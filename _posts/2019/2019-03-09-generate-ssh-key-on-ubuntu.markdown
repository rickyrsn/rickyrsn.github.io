---
layout: post
title:  "Generate SSH Key on Ubuntu"
date:   2019-03-09 19:00:00 +0700
---
## Create SSH Key Pair
>$ ssh-keygen

##### Optional
add flag -b 4012 to create 4012-bit key
>$ ssh-keygen -b 4012

Output :
>Generating public/private rsa key pair.
>Enter file in which to save the key (/your_home/.ssh/id_rsa):

Press ENTER to save the key pair into the .ssh/ subdirectory in your home directory, or specify an alternate path.