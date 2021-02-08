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

I thought it would be easier to put them in a blog for future reference. I generally take an Ubuntu instance and most of my commands are ubuntu commands please change the commands accordingly. I also use a VScode SSH remote extension to connect to the instance so that I can use VScode for remote development. 

### Generating the SSH key

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

substitute the github email address at "your_email@example.com" 

Source: [SSH keygen](https://docs.github.com/en/github-ae@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

This will generate a private and public key pair at `~/.ssh/` in the local file system

Now `cd ~/.ssh/` if your key is named differently select the corresponding location and copy it. 

I generally do `cat id_rsa.pub` and then copy the output in the terminal. Go to settings in GitHub user profile and paste your key in SSH and GPG keys and name it appropriately. 

### Creating Anaconda Environment

- Download Miniconda (I prefer it to anaconda as it is light and comes with very basic framework while conda is a monstrous piece of software which sometimes is a luxury to install on small VM's)

Source : [Install miniconda on Terminal](https://waylonwalker.com/install-miniconda)

```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
~/miniconda3/bin/conda init bash
```
restart the shell and we are ready to start

- Create a new environment

`conda create -n env_name` replace `env_name` with the name of your environment. 

- Activate environment 

`conda activate env_name` activates the environment 

`conda deactivate` deactivates the environment

#### Problems to be solved
Sometimes the conda environment created is empty and in that case I do install pip and python manually by using

`conda install python==version` and `conda install pip`

*As of Feb 2021 it is better to install python 3.8 as the dependencies on are easier for data science packages*

#### Requirements file

Write a requirements file as a part of your repository to install the necessary packages

General structure of the requirements.txt are

```
numpy
scipy
matplotlib
pandas
...

```
#### Installing with Pip

Some packages that I use for development are not on conda so I use pip to install.

`pip install -r requirements.txt`

Now the package is setup with the requirements and a conda environment and can be used for development. 



