---
layout: post
title:  "Terminal Makeover"
date:   2023-01-28 18:45:00 +0100
comments: True
share: True
categories: Tools
---

Recently I had a talk with a senior engineer from my organisation and he was an advocate for better looking terminal with oh-my-zsh and themes. His argument was Bash terminals are boring and since he was a nvim user he wanted to give the terminal a makeover. So I came under the spell of his good looking terminals and decided to experiment by changing terminals in my personal notebook which runs an Ubuntu 20.04. Here are the steps that I did and the way you can replicate them for your terminal too. 

Most of the blog is a mixture of my steps in transforming my terminal from bash to zsh and learning taken from other blogs, I have tried to cite them as much as possible. If something is left out I apologise for it now. 

### Step1: Download and install oh-my-zsh
```
sudo apt-get install zsh
```
check if it is installed by ``` zsh --version```

### Step2: Change shell
Though the zsh is installed we need to change the shell from bash to zsh, we can do that by
``` 
chsh -s $(which zsh)

```
### Step3: Setup .zshrc
 If you are using zsh for the first time there will be no file called .zshrc in the ```/home/``` folder so create one and copy all contents of ```~/.bashrc``` to ```~/.zshrc```

### Step4: Setup a theme 
I tried different themes and came to a conclusion that agnoster is the best theme for my usage it is clean and shows relevant information in a clean way. But since I am no evangelist I would suggest to take a look many tutorials which suggests different fonts and themes here. For choosing agnoster it is as simple as selecting 

```
ZSH_THEME="agnoster"
```


