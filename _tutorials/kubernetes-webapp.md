---
layout: tutorial
title: Web App Deployment
description: A simple recipe for deploying a small web app to Kubernetes.
categories: [kubernetes, kubernetes, tutorial]
permalink: /tutorials/kubernetes/simple-web-app:output_ext
header-img: /assets/img/kubernetes-horizontal-color.png
date: 2020-11-26
parent: ['/tutorials/kubernetes/', 'Kubernetes']
---
[Kubernetes](https://kubernetes.io/) is a powerful container orchestration system originally developed by Google. It has recently seen an explosion in popularity, even gaining native support by major vendors such as [Ubuntu](https://ubuntu.com/kubernetes).

At my current employer, one of my duties is to help maintain our on-prem, bare-metal installation. I develop utilities and resources to aid researchers, and use it myself to train and evaluate new models.

One utility that I recently developed was a small web application for launching single pods as we are blocked by a bugged Kubeflow installation.

What follows is a reduced example demonstrating what I learned in the process of making said utility.

<div class="mx-auto" style="width: 50%">
<table class="table">
<thead class="thead-light"><h2>Table of Contents</h2></thead>
<tbody>
<tr>
<td>
<a href="#step-1-the-container"><u><em>Step 1: The Container</em></u></a>
</td>
</tr>
<tr>
<td>
<a href="#step-2-the-deployment"><u><em>Step 2: The Deployment</em></u></a>
</td>
</tr>
<tr>
<td>
<a href="#step-3-the-service"><u><em>Step 3: The Service</em></u></a>
</td>
</tr>
<tr>
<td>
<a href="#step-4-the-ingress"><u><em>Step 4: The Ingress</em></u></a>
</td>
</tr>
</tbody>
</table>
</div>

# Step 1: The Container
The first step in our recipe is to, of course, create our web app and package it inside of a Docker container.

For this example, we will create a simple 'Hello World' Flask app in Python.

The following will be saved as `hello.py` in our project directory:

``` python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```

Now that we have our code, we have to throw it into a Docker image. Here is my Dockerfile:

``` dockerfile
FROM python:3.7

ADD . /opt/

WORKDIR /opt/

ENV FLASK_APP=hello.py
CMD flask run --host=0.0.0.0
```

I'll explain each line here in detail:
- `FROM python:3.7`
    - You can base your image off of any image, but this works the best for me personally and I prefer Python 3.7.
- `ADD . /opt/`
    - This adds our current directory to `/opt/` inside the container. My personal style is to use `/opt/` as the default place for things like this inside containers.
- `WORKDIR /opt/`
    - Change where our commands get executed, so that our container can find our fancy app.
- `ENV FLASK_APP=hello.py`
    - This environment variable lets Flask know where our app's code is located.
- `CMD flask run --host=0.0.0.0`
    - This overrideable command starts Flask at `0.0.0.0`. *This is very important*. In order for us to access this outside of the container, the host must be set to this (in my experience).

Now we push this to our repository. **This repository must be accessible from your cluster.**

`docker build . -t $REPOSITORY/$IMAGE:$TAG`

# Step 2: The Deployment
Now that we have our Docker image built and pushed to our repository, we now get to the exciting part of deploying it to our cluster. The following *YAML* creates a very simple deployment with one pod:


```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myflaskapp
  labels:
    app: myflaskapp
spec:
  replicas: 1
  selector:
    matchLabels:
      app: myflaskapp
  template:
    metadata:
      labels:
        app: myflaskapp
    spec:
      containers:
      - name: myflaskapp
        image: $REPOSITORY/$IMAGE:$TAG
        ports:
        - containerPort: 5000
```

Heres's what's going on inside this file:
- `app: myflaskapp` This field in the metadata and spec ensures that any pods created by this template are associated with this deployment.
- `containerPort: 5000` This exposes port 5000 inside the container, as that is the default port for Flask. This is configurable.

Let's save this *YAML* as `deployment.yaml` and apply with `kubectl apply -f deployment.yaml`

# Step 3: The Service
Now that we have our pod running inside a deployment, let's expose it as a service to the rest of the cluster.

``` yaml
apiVersion: v1
kind: Service
metadata:
  name: myflaskapp-service
spec:
  selector:
    app: myflaskapp
  type: ClusterIP
  ports:
  - protocol: TCP
    port: 5000
    targetPort: 5000
```

Let's once again analyze what I'm doing here:
- `app: myflaskapp` We once again make sure to select our app in order to associate this with our deployment.
- `type: ClusterIP` This creates a cluster-internal IP address for this service. This is also the default service type.
- `port:5000` This exposes port 5000 at our newly-assigned IP.
- `targetPort:5000` Forward the aforementioned port to port 5000 in our pod.

Similar to above, we'll save this `YAML` as `service.yaml` and commit it as such: `kubectl apply -f service.yaml`

# Step 4: The Ingress
Final step, we're almost there! Now we must expose this service to the outside world. This section is highly dependent on the configuration of your cluster and whether or not you are operating in the cloud. This basic configuration should be good enough for a bare-metal installation such as mine.

``` yaml
apiVersion: networking.k8s.io/v1beta1
kind: Ingress
metadata:
  name: myflaskapp
  annotations:
    kubernetes.io/ingress.class: "nginx"
    nginx.ingress.kubernetes.io/rewrite-target: $1
spec:
  rules:
  - http:
    paths:
    - path: /myflaskapp/(.*)
      pathType: Prefix
      backend:
        serviceName: myflaskapp-service
        servicePort: 5000
```

One assumption made here is that your cluster also uses the [NGinx ingress controller](https://kubernetes.github.io/ingress-nginx/).

Heres what the above *YAML* accomplishes:
- `nginx.ingress.kubernetes.io/rewrite-target: $1` This ensures that the request that is sent to our container is in the form `$HOST/$SOMETHING` instead of in the form `$HOST/myflaskapp/$SOMETHING` as we did not configure our server to handle that route.
- `path: /myflaskapp/(.*)` This helps accomplish the above bullet. The regex group at the end is what is captured in the `$1` variable above.
- `pathType: Prefix` Does a case-sensitive match of the any paths/subpaths prefixed by our above path.

Now we save this final *YAML* as `ingress.yaml` and apply it via `kubectl apply -f ingress.yaml`


# Fin
And there we have it. Assuming that I'm worth my salt and you managed to stomach my verbosity, you should now be able to navigate to `http://$NODEIP:$INGRESSPORT/myflaskapp/` and see our "Hello, World!" from earlier.

*Note: `$NODEIP` is the IP address of one of the nodes in your cluster and `$INGRESSPORT` is the node port which your ingress controller services.*