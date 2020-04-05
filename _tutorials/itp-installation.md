---
layout: tutorial
title: Installation
description: Simple guide to get started with Python!
categories: [intro-to-python, python, tutorial]
header-img: /assets/img//assets/img/woman-programming-on-a-notebook-1181359.jpg
permalink: /tutorials/intro-to-python/installation:output_ext
date: 2019-03-25
parent: ['/tutorials/intro-to-python.html', 'Intro to Python']
---

This first tutorial will cover how to get Python installed on your computer and setting up your coding environment. I will be targeting Mac, but the instructions are identical for Windows. This process is very easy, and certainly the most important. Don't be intimidated by the length of these tutorials, I'm just rather verbose.

# Download
---
The first step, of course, is to go [here](https://www.python.org/download) and click this shiny button:

<img src="{{ '/assets/img/download_butt.png' | absolute_url }}" class="rounded mx-auto d-block" style="width:50%;">

This will download the installer to your computer. Open that file and follow the prompts. I won't insult your intelligence and leave this part to you.

For Windows users, make sure to check the "Add Python to PATH" checkbox in the installer.

Congratulations, you now have Python! You should now be presented with the following files:

<img src="{{ '/assets/img/new_files.png' | absolute_url }}" class="rounded mx-auto d-block" style="width:50%;">

I'll go over the files that you see here:

<table class="table table-striped">
        <tbody><tr><th>IDLE</th>
        <td>Potentially your new best friend. This is an interactive environment for writing and executing Python.</td></tr>
        <tr><th>Install Certificates.command</th>
          <td> This file will execute a command on your computer to install specially-curated SSL root certificates. You shouldn't have to worry about this now.</td></tr>
        <tr><th>License.rtf</th>
          <td>The license that Python is released under. I'm sure we'll all thoroughly read this.</td></tr>
        <tr><th>Python Documentation.html</th>
          <td> Self-explanatory, opens the documentation for Python in a web browser. Highly recommend reading this some time.</td></tr>
        <tr><th>Python Launcher</th>
          <td>This file is solely for your computer to run, don't worry about it.</td></tr>
        <tr><th>README.rtf</th>
          <td>Arguably the most important file in any software project. Gives you some useful info about Python.</td></tr>
        <tr><th>Update Shell Profile.command</th>
        <td>Makes sure that Python is opened when you type "python" in a shell window. If you wish to use the terminal (more on this below), run this.</td></tr>
      </tbody>
</table>

# Editor
---
This is the fun part: Deciding where you want to develop.

It's totally okay to stick with IDLE as it lets you create scripts as well as interactively execute code. IDLE also provides handy suggestions as you type. If it's not your style, any text editor or <a href="#" data-toggle="tooltip" data-original-title="Integrated Development Environment" data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">IDE</a> will work just fine. I know that [Atom](https://atom.io/) is a very popular choice as it's gorgeous, simple, and extendible. Personally, if I'm not using VIM (A command-line editor), I use [PyCharm](https://www.jetbrains.com/pycharm/). However, that may be a little overkill for a beginner and it can be a bit overwhelming. The choice is truly yours, but I highly recommend an editor made specifically for programming as it'll provide highlighting and corrections which will prove very useful.

# Workspace
---
Finally, we should set up where you will do all your work. Go ahead and create a folder anywhere on your computer called "python_workspace". You can place it anywhere you won't forget it, but I recommend placing it in your Documents folder. This will house all your future projects and their <a href="#" data-toggle="tooltip" data-original-title="A place to safely install things specifically for a single project." data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">virtual environments</a>.

After you decide on an editor and create the folder, we're all set! Sweet!!
