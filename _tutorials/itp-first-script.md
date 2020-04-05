---
layout: tutorial
title: Your First Script
description: Let's get nerdy 
categories: [intro-to-python, python, tutorial]
permalink: /tutorials/intro-to-python/firstscript:output_ext
header-img: /assets/img/post-bg.jpg
date: 2019-03-27
parent: ['/tutorials/intro-to-python.html', 'Intro to Python']
---

Welcome back! I know what you're thinking: "But Nick! I'm not ready to start programming yet, I just downloaded Python for crying out loud!" but trust me, it really is that easy. Plus, I'll teach some important things along the way.

# Environment
---
Before we get to coding, we need to make sure you get into the habit of having good project structure. In your "python_workspace" folder we created in the last tutorial, create a folder called "myfirstscript". In that folder, we will create a new file called "myfirstscript.py" using IDLE. If you followed the extra tutorial, and I highly recommend that you do, open your terminal and type the following:

```python
cd Documents/python_workspace/myfirstscript/
```

Adjusting the second part if you placed your workspace folder anywhere but Documents. Using the terminal will allow you to use whichever editor you like.

# Hello World
---
Now that you have the python script open, write the following line:

```python
print("hello world")
```

Save the file and click `Run > Run Module` in the menu. This should then open a new IDLE window where you will see the message "Hello, World!" written to your screen. Yay, you just ran your first ever Python program!

For you users that opened the terminal in the last section, you can type `python myfirstscript.py` and you should see the same results on the next line.

# Variables
---
The last part was a great way to introduce you to running a script, but it didn't really do anything! That's the whole reason we invented computers! So now, we'll make it actually do something.

Back in your script, delete that print line we wrote, you won't need it anymore. We're off to bigger and better things. In it's place, write the following lines:

```python
x = 1
y = 2
z = x+y
```

*x*, *y*, and *z* are what's known as *variables*. Yes, just like variables in math. They hold values that you give them and they will be your work horses. You'll notice that I put each variable <a href="#" data-toggle="tooltip" data-original-title="The first time a variable is defined." data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">declaration</a> on it's own line. In Python, each line represents a single command for it to execute. Now add the following line at the end: `print(z)`. Save and run the file. You should see the number "3" printed out.

To summarize, you gave *x* the value of 1, *y* the value of 2, and *z* the value of *x* plus the value of *y*. These variables are what's known as *integers*. Again, just like math. They represent whole numbers. You were also introduced to *strings* in the first print statement. Strings are always surrounded by quotation marks and they represent plain text, nothing special. There are many other variable types that we'll touch on in the future.

One final note: variable names should always be as succinct as possible, and lowercase. If you must use two words, connect them with an underscore (i.e. `account_number`) as Python uses spaces as a <a href="#" data-toggle="tooltip" data-original-title="Some sort of symbol that differentiates seperate items." data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">delimiter</a>, similarly to English. Code is read more than it is written, and you will save future you (and maybe someone else) a lot of trouble if you follow these simple rules.

# Conclusion
---
That's all for this tutorial! If you made it this far, thank you and I'm proud of you. In the next one we'll do more fun and useful things with variables. For now, I highly suggest you spend some time playing with what I have taught you so far. Have fun and go crazy!
