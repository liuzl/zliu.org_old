+++
date = "2015-07-14T19:46:04+08:00"
draft = true
title = "python virtualenv"
categories = [
    "development", "python"
]
+++

A Virtual Environment is a tool to keep the dependencies required by different projects in seperate places, by creating virtual Python environments for them. It solves the "Project X depends on version 1.x but, Project Y needs 4.x" dilemma, and keeps your global site-packages directory clean and manageable.<!--more-->

For example, you can work on a project which requires Django 1.3 while also maintaining a project which requires Django 1.0.

## virtualenv
[virtualenv](https://pypi.python.org/pypi/virtualenv) is a tool to create isolated Python environments, virtualenv creates a folder which contains all the necessary executables(including the python and pip executables) to use the packages that a Python project would need. And also virtualenv makes the deploy of a Python system very convenient(just copy the virtualenv folder to a target machine).

Install virtual via pip:

`$pip install virtualenv`

## Basic Usage
Create a virtual environment for a project:

`$virtualenv env_folder`

virtualenv env_folder will create a folder in the current directory which will contain the Python executables files, and a copy of the pip library which you can use to install other packages. The name of the virtual environment(in this case, it was env_folder) can be anything, omitting the name will place the files in the current directory instead.

You can also use a Python interpreter of your choice.

`$virtualenv -p /usr/bin/python2.4 env_folder`

This will use the Python interpreter in /usr/bin/python2.4

To begin using the virtual environment, it needs to be activated:

`$source env_folder/bin/activate`

The name of the current virtual environment will now appear on the left of the prompt(e.g. (env_folder)Your-Computer:your_project UserName$) to let you know that it's active. From now on, any package that you install using pip will be placed in the env_folder, isolated from the global Python installation.

Install packages as usual, for example:

`$pip install requests`

If you are done working in the virtual environment from the moment, you can deactivate it:

`$deactivate`

This puts you back to the system's default Python interpreter with all its installed libraries.

To delete a virtual environment, just delete its folder.

