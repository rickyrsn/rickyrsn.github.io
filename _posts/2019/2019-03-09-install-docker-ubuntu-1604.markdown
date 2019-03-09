---
layout: post
title:  "Basic Linux - Add User"
date:   2019-03-09 19:15:00 +0700
---
# Install Dependencies

First, we need to add the GPG key for official Docker repo
> `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

Then add Docker repository to APT sources:
>`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`

Next, we need to update the package:
>`sudo apt-get update`

Make sure we are about to install Docker from official Docker repo, not ubuntu repo
>`sudo apt-cache policy docker-ce`

Then, you should see the output similar to the follow:
```conf
docker-ce:
  Installed: (none)
  Candidate: 18.03.0~ce-0~ubuntu
  Version table:
     18.03.0~ce-0~ubuntu 500
        500 https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
.     17.12.1~ce-0~ubuntu 500
        500 https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
```

# Install Docker
Finally, install Docker:
>`sudo apt-get install -y docker-ce`

Enable Docker to start on boot:
>`sudo systemctl enable docker`

Executing Docker without sudo:
```conf
sudo usermod -aG docker ${USER}
```

Now check your membership, and confirm that your user is now added to Docker group
```s
su - ${USER}`
id -nG`
```

Optionally, if you need to add user to docker group that you are not logged in as, you can use:
>`sudo usermod -aG docker type_your_username`