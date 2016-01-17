+++
date = "2015-12-30T12:54:55+08:00"
draft = true
title = "Installation of java8 on ubuntu"
categories = [
    "development", "java", "ubuntu"
]
+++

The installation of Java8 on Ubuntu system is quite simple, mainly two steps: first, adding the ppa source; second, using apt-get to install.
<!--more-->
Details are as follows:

`sudo add-apt-repository ppa:webupd8team/java`

`sudo apt-get update`

`sudo apt-get install oracle-java8-installer`

