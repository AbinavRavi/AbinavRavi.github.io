---
layout: post
title:  "Cost Functions and Loss Functions in Machine Learning"
date:   2023-02-14 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---
## AIM OF MACHINE LEARNING

Machine Learning or Deep Learning can be viewed as function approximation based on data. What this means in simpler terms is that given a set of data points the aim is to get a function that can represent each of the data point very well and this function generalizes across many such similar data points. 

A simple polynomial curve fitting example is shown below. The idea of machine learning is to achieve something similar to left bottom figure so that there is a little bit of generalization or extrapolation that can be done if a sample comes from similar distribution. 

![Function Approximation](../ml/back2basics/curve_fitting.jpeg) [1]
 
In case of the first diagram
### LOSS FUNCTION
Loss function is the function that can depict the error between the predicted function value at a data point and the actual value. Loss functions are measured over single datum points. 

### COST FUNCTION
Cost function also denotes the error between predicted value and actual value but for a batch of data values. 

### MATHEMATICAL PROPERTIES OF LOSS FUNCTION
For a loss function these mathematical properties are important

- Differentiable in real domain completely
- Possibly convex to ensure that there is a minimum, but in case of deep learning the loss function landscape will generally not be convex and we will have to do with the local minimum.
### MOST COMMON LOSS FUNCTIONS 

- **Cross Entropy Loss**

- **Mean Squared Error**




## References

 1. Figure 1.4, [Pattern Recognition and Machine Learning, Christoher Bishop](https://www.microsoft.com/en-us/research/uploads/prod/2006/01/Bishop-Pattern-Recognition-and-Machine-Learning-2006.pdf) 


