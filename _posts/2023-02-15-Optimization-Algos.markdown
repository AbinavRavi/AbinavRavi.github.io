---
layout: post
title:  "Common Optimization Algorithms"
date:   2023-02-16 22:45:00 +0100
comments: True
share: True
categories: Machine learning
---

## The Learning Process

An important question to ask is what does it mean to learn in Machine Learning/Deep Learning? The answer is simple the goal of a Machine Learning model is to represent the knowledge of most data points with the help of a function which can either be linear or non linear. So how do we decide which function to choose to represent the data points? We use weights and biases to represent the function and randomly assign them a value, then we go on to then iteratively modify the weights with the help of cost function/loss function. When we minimize the cost function we then bring the prediction function closer to the data points. 

How to go about the minimization process? For this we use the optimization algorithms such as gradient descent, Stochastic gradient descent etc

## The Gradient Descent Algorithm
The gradient descent algorithm is a first order optimization method which means that the highest order of derivative is first derivative. 
For gradient descent to be applied on the function there are two basic requirements.
The function must be
1. Differentiable - Derivative exists in all points of the domain of concern
2. Convex - The second derivative is a positive value i.e. the function has one minimum value

### What is a gradient?

In univariate calculus it is a derivate of the function and in multivariate calculus it represents the vector of derivatives with respect to a certain direction. 

### Algorithm

The gradient descent algorithm is an iterative process (happens in a loop) until convergence is achieved. In layman terms consider moving down a mountain gradient descent can be said as the shortest number of steps that would be required to reach the valley. The pace at which we can get down is limited by the length of the steps and this is analogous to learning rate. If I were 30 ft tall I will reach in 5 steps opposed to 25 odd steps if I were 6ft tall. 

Please find a simple implementation of gradient descent in python below

```Python
import numpy as np

def gradient_descent(start, gradient, learn_rate, max_iter, tol=0.01):
  steps = [start] # history tracking
  x = start

  for _ in range(max_iter):
    diff = learn_rate*gradient(x)
    if np.abs(diff)<tol:
      break    
    x = x - diff
    steps.append(x) # history tracing

  return steps, x
```
The code is from [this blog](https://towardsdatascience.com/gradient-descent-algorithm-a-deep-dive-cf04e8115f21#:~:text=Gradient%20descent%20(GD)%20is%20an,e.g.%20in%20a%20linear%20regression)
### Disadvantage.

Though the approach is quite clean cut, since we are dealing with a large number of samples the calculation of the next step after going through all samples is very computation intensive. This is where there is a need for stochasticity and working in smaller batches and iterations. This method of performing gradient descent for random batches is known as **Stochastic Gradient Descent**.
### Momentum

## ADAM optimization

## Other optimization algorithms 


