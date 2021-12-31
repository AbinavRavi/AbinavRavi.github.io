---
layout: post
title:  "How to convert jupyter notebook model into a microservice - Part 1: Structuing the repository"
date:   2021-01-02 18:45:00 +0100
comments: True
share: True
categories: Engineering
---

Welcome to part 1 of the 6 part series on Converting your jupyter notebook machine learning model to microservice

There are multiple posts on how to write a model and different types of models on the internet and that is not the focus of this blog post. This series helps structure that model into microservice which can be like a lego block serving the model. I will not be using Kubeflow, MLflow etc for this purpose. 

# What kind of model are we doing this for?

I will focus on doing this for a simple open source deep learning model of FashionMNIST trained on Tensorflow or pytorch (Doesnt really matter). So the inputs can be anything but the process would be that we convert the image to **28x28x1** as input and then run inference and if the model doesn't belong to any of the class we should be able to get a error message. 

If you need to train a fashion MNIST model Please follow the following resources and they have wonderful step by step for you to train the model

- [Tensorflow](https://www.tensorflow.org/tutorials/keras/classification)
- [Pytorch](https://github.com/AbinavRavi/Model2Service) - You can find a jupyter notebook model for understanding the model building process under notebooks folder

# Issue with Jupyter notebooks

Until very recent past and without specific tools it is difficult to use jupyter notebooks for running production grade models, Notebooks are fun to learn and I still use them to run my experiments and check a new functionality but they are hard to maintain version control over. So we convert these jupyter notebook models into refactored (big word for splitting notebook into functions and classes) scripts that can work smoothly without supervision.

# Focus of this post

In this post we will cover establishing some basic components apart from refactoring such as pre-commit which imposes a strict discipline and styling requirements to commit code. 



# What is Linting
Linting is a static code analysis tool to catch bugs, errors and stylistic errors. Fun fact is that the term come from actual lint which is the textile mass that is shed by clothes. The idea was that Linting could capture the stylistic errors like a lint trap.  
# Why do we need linting

# What tools help do linting?
write about black, flake8, bandit, [Pep8](https://www.python.org/dev/peps/pep-0008/)
# How to force linting practice?
pre-commit configuration ensures code stays in same structure even as we need to commit it
