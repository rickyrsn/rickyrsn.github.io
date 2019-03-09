---
layout: post
title:  "Basic Linux - Add User"
date:   2019-03-09 19:15:00 +0700
---
# Step to create new user

First, you must login as root user

Add User
> adduser username

Set & Confirm new user password :
> Set password prompts:
> Enter new UNIX password:
> Retype new UNIX password:
> passwd: password updated successfully

Set & Confirm new user information :
> User information prompts:
> Changing the user information for username
> Enter the new value, or press ENTER for the default
> Full Name []:
> Room Number []:
> Work Phone []:
> Home Phone []:
> Other []:
> Is the information correct? [Y/n]

# Add User to a Group
> usermod -aG groupname username
> 

# Test sudo access
> su - username
> whoami
