---
layout: post
title:  "Installing Vagrant on Ubuntu 16.04"
date:   2019-03-09 19:40:00 +0700
---
# Installation

Make sure you are logged with sudo/root

```s
$ sudo apt-get install virtualbox
$ sudo apt-get install vagrant
```

Verify Vagrant Installation

```s
$ vagrant --version
```

# Create Project

```s
$ mkdir ~/project1
$ cd ~/project1
$ vagrant init ubuntu
$ vagrant up
```