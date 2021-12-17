---
layout: post
title:  "How to make effective use of bash terminal -Part 1"
date:   2020-1-5 18:45:00 +0100
comments: True
share: True
categories: General tools
---

# Why do we need a terminal?

This is the first question that people ask when they migrate from the GUI of Windows systems and linux seems very intimidating. In this blog I will try to pacify this fear for the terminal and geeky stuff with examples. If the aim is to work with any backend systems or servers at any point the usage of terminal is warranted. In this blog we will basically cover file system operations and few basic commands in terminal and bash scripting basics. 

# Why one more blog on bash scripting?

My experience with terminals was pacified after a continuous usage and in the beginning it was very intimidating and daunting, the aim of this blog is to help execute certain small commands and help a transition into the Linux subsystems. If the reader prefers a visual method of learning I will attach few youtube videos in the bottom as reference where readers can go and follow around. 

# The story begins !!

I was about to get into graduate school in 2017 and had studied mechanical engineering in my bachelors and had very less programming experience, I had used vi to program in my computer science lab in C programming and the next thing I was doing was making plots after learning some python using Matplotlib in my Bachelor thesis/project. I had heard from a friend that getting some knowledge of Linux basics is essential to navigate around and will make graduate school life easier (PS: He was studying the same course but in a year above). So I dual booted a Ubuntu system the most used linux distribution. 

The terminal has a 80s look to it, a black screen with a serif font and a blinking cursor which reminds us of the hackers or old computers of the past. But it is not necessary that the terminal looks that way all the time, there are variety of options available for a terminal shell such as 

- Shell
- Bash
- Zsh
- Fish etc

In this case we will work with a bash shell, since it is more new and useful and there are multiple articles on the internet where we can customize a terminal to look great and feel great. But that is not the aim of this piece.

# How do I visualise a file system using the terminal?

For most people who have been used to GUI based OS this part of visualising a file system through the terminal will be overwhelming but when you tame these commands and make it yours it will be easy and satisfying.

```bash
pwd
ls
mkdir
cd
clear
rm 
mv 
cp
touch
open
echo
```

A new terminal always starts at the home directory