---
layout: default
title: Projects
permalink: /projects/
header-img: assets/img/books-business-computer-connection-459654.jpg
---
<div class="row mt-3">
        <div class="col-sm-4">
            <img src="{{ '/assets/img/Janus_logo_72dpi-01.png' | absolute_url }}" alt="Janus Logo" class="img-responsive img-thumbnail" width="100%">
        </div>
        <div class="col">
            <h3 align="center">IARPA Janus</h3>
            <p align="center"><a href="https://www.iarpa.gov/index.php/research-programs/janus">Project Link</a></p>
            <p class="mt-0">
            Through my previous employer, Noblis, I was provided the opportunity to work on many advanced research projects. One such project that I was able to contribute to was the IARPA Janus program.  </p>
            

            <p class="mt-0">
            <b>My contribution:</b>
            <br>
            For this program, I developed a Python pipeline that enabled the flow of a large number of Human Intelligence Tasks (HITs) to and from Amazon Mechanical Turk for the <a href="https://noblis.org/wp-content/uploads/2018/03/icb2018.pdf">IJB-C Dataset</a>. More minor tasks included integrating a standard facial recognition algorithm into the API used for this project to provide a baseline benchmark and generating evaluation results that were directly delivered to clients.</p>
        </div>
</div>
<br>
<div class="row mt-3">
        <div class="col-sm-4">
            <img src="{{ '/assets/img/TSA.png' | absolute_url }}" alt="TSA logo" class="img-responsive img-thumbnail" width="100%">
        </div>
        <div class="col">
            <h3 align="center">TSA Passenger Screening Challenge</h3>
            <p align="center"><a href="https://www.kaggle.com/c/passenger-screening-algorithm-challenge/leaderboard">Project Link</a></p>
            <p class="mt-0">
            My participation in this challenge was funded via an internal research project at Noblis. Despite entering towards the latter half of the competition, our team managed to place within the top 6% of all participants. </p>
            

            <p class="mt-0">
            <b>My contribution:</b>
            <br>
            For this project, my manager experimented with rotating tasks between pairs of programmers. As a result, I had the opportunity to contribute to many sides of this project. My first task was to implement basic computer vision functionality such as convex hull to clean up the data as well as the ability to render 2D views of the 3D data at arbitrary angles. I also developed the evaluation harness for the final testing of the model developed by our team before submission.</p>
        </div>
</div>
<br>
<div class="row mt-3">
        <div class="col-sm-4">
            <img src="{{ '/assets/img/CMRALogo.jpg' | absolute_url }}" alt="CMRA logo" class="img-responsive img-thumbnail" width="100%">
        </div>
        <div class="col">
            <h3 align="center">NSF RD-AIM-HIRE</h3>
            <p align="center"><a href="https://www.cmu.edu/roboticsacademy/Research/rd-aim-hire.html">Project Link</a></p>
            <p class="mt-0">
            This project was one of my first projects through the National Robotics Engineering Center. The aim of this project was to develop an ML professional development program for displaced workers to provide them with the skills necessary to remain competitive in the new Industry 4.0. </p>
            

            <p class="mt-0">
            <b>My contribution:</b>
            <br>
            Leveraging skills learned through my previous employer, I provided guidance for deploying this new program to Amazon Web Services at-scale. This meant providing the ability for toy models to be trained in the cloud on demand and run in-browser for lightweight inference in this gamified training experience. We were able to train simple MLP and linear regression models on thousands of data samples in under 10 seconds and return them to the user for rapid, in-browser inference.</p>
        </div>
</div>
<br>
<div class="row mt-3">
        <div class="col-sm-4">
            <img src="{{ '/assets/img/ArmyFuturesCommand.png' | absolute_url }}" alt="Army Futures Command Logo" class="img-responsive img-thumbnail" width="100%">
        </div>
        <div class="col">
            <h3 align="center">Aided Threat Recognition from Mobile Cooperative and Autonomous Sensors</h3>
            <p align="center"><a href="https://www.army.mil/article/232074/aided_detection_on_the_future_battlefield">Project Link</a></p>
            <p class="mt-0">
            My main project at the National Robotics Engineering Center is a collaboration with the Army AI Task Force to develop a cooperative and autonomous off-road vehicle and drone with threat recognition capability. This project has proved to be an interesting challenge as we push the limits of ML inference time on constrained hardware capabilities.</p>
            

            <p class="mt-0">
            <b>My contribution:</b>
            <br>
            For this project, I have developed a data pipeline and artifact manager, written mostly in Python. This pipeline is capable of the following:
            <ul>
            <li>Preparing raw data coming off our custom hardware for manual data segmentation.</li>
            <li>Generating Jira tickets for the labeler in charge of the segmentation.</li>
            <li>Uploading these new segments to a data annotation tool for a team of labelers to generate segmentation and object detection annotations, both 2D and 3D.</li>
            <li>Generating datasets for researchers to train and evaluate new models.</li>
            <li>Automatic testing and evaluation of these new models.</li>
            <li>Tracking of the artifacts of all the above steps in a PostgreSQL database.</li>
            </ul>
            
            I have also contributed to the C++ code base that runs on the vehicle itself by implementing an image stitching tool using OpenCV for visualization as well as integrating a Tensorflow implementation of the YOLOv3 model for a baseline detection model. Other minor tasks include creating a tool for extracting raw and rectified images and point clouds from the raw data in support of the aforementioned data pipeline.</p>
        </div>
</div>
