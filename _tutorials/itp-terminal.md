---
layout: tutorial
title: "Extra: Using the Terminal"
description: "Alternate title: How to Look Like a Hollywood Hacker"
categories: [intro-to-programming-with-python, python, tutorial]
permalink: /tutorials/intro-to-programming-with-python/terminal:output_ext
header-img: /assets/img/woman-programming-on-a-notebook-1181359.jpg
date: 2019-03-26
parent: ['/tutorials/intro-to-programming-with-python/', 'Intro to Python']
---

So it comes to this. I've tried to keep all of this rather basic, but there's just one thing we must do: use the terminal. In Windows, it's called Command Prompt, and in Mac or Linux it's just called Terminal. This tool provides a text-based method for interacting with your computer. It's the thing at which you see all the Hollywood hackers furiously typing away. For us, it will provide the ability to run Python with <a href="#" data-toggle="tooltip" data-original-title="Information or options we pass to programs from the terminal." data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">command-line arguments</a>.

# The Basics
---
Go ahead and open the appropriate program for your Operating System. Windows users, search for "cmd" or "Command Prompt". Everyone else, search "Terminal". You should be presented with a very plain, black window with some information. Where your cursor is currently blinking is called the command prompt, because it is prompting you for a command. Next to your cursor you should see something like `C:\Users\Nick`. This is where you currently are and where anything you do will happen. In the following sections I'll explain some basic navigation for your Operating System.

# Mac / Linux
---
Congratulations, you have the easier terminal to use (in my opinion). First, let's explore the directory (folder) you're currently in. Type `ls` (short for list) and press Enter/Return. This will list every file in your current directory. You should see stuff like your Documents folder, Downloads folder, etc. Where you are now is called your root directory. It's the starting point for your specific account on that computer. Now that we know where we are and how to look around, how do we move? That's where the `cd` (short for change directory) command comes in. Go ahead and try `cd Documents` followed by `ls` again. After you change directories, you should see your prompt change to reflect this. After the `ls` command, you should see the the files in your Documents folder. If you ever get lost, you can do `cd ~` to get back to your root directory. `~` is a handy shortcut that represents your root directory's <a href="#" data-toggle="tooltip" data-original-title="The 'directions' to a folder or file." data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">path</a>. This should be sufficient knowledge for you for now, play around with it a bit to get familiar.

# Windows
---
You just had to be different. This section exists solely because Windows is the only major Operating System with a different terminal. I'm going to shamelessly copy/paste the last section and adjust it for Windows here:

First, let's explore the directory (folder) you're currently in. Type `dir` (short for directory) and press Enter/Return. This will list every file in your current directory. You should see stuff like your Documents folder, Downloads folder, etc. Where you are now is called your root directory. It's the starting point for your specific account on that computer. Now that we know where we are and how to look around, how do we move? That's where the `cd` (short for change directory) command comes in. Go ahead and try `cd Documents` followed by `dir` again. After you change directories, you should see your prompt change to reflect this new <a href="#" data-toggle="tooltip" data-original-title="The 'directions' to a folder or file." data-placement="bottom" style="text-decoration:none; border-bottom: 1px dashed grey;" onclick="return false;">path</a>. After the `dir` command, you should see the the files in your Documents folder. This should be sufficient knowledge for you for now, play around with it a bit to get familiar.
