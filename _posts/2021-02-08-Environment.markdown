---
layout: post
title:  "Setting up VM instance"
date:   2020-11-22 18:45:00 +0100
comments: True
share: True
categories: Engineering
---
There are numerous tutorials individually on what to do for multiple steps that I do while setting up a new instance such as 

1. Generating a SSH key and adding to the Github settings.
2. Creating an anaconda environment and setting up the requirements
3. Issues which come I generally face while creating environment and how I solve them

I thought it would be easier to put them in a blog for future reference. 

**Generating the SSH key**

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

substitute the github email address at "your_email@example.com" 

Source: [SSH keygen](https://docs.github.com/en/github-ae@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

This will generate a private and public key pair at `~/.ssh/` in the local file system

Now `cd ~/.ssh/` if your key is named differently select the corresponding location and copy it. 

I generally do `cat id_rsa.pub` and then copy the output in the terminal. Go to settings in GitHub user profile and paste your key in SSH and GPG keys and name it appropriately. 

**Creating Anaconda Environment**

