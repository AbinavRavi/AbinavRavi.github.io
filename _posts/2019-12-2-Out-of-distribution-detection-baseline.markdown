---
layout: post
title:  "Baseline for Out of Distribution Detection"
date:   2019-12-07 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---

Two data scientists Tom and Jerry are discussing a paper titled [A baseline for detecting misclassified and Out of distribution examples in Neural networks](https://arxiv.org/abs/1610.02136).

#### Introduction:
**Tom**: A Neural network(NN) trains on a given set of data and during deployment(test time) it is unrealistic to expect the same distribution from the test data as well. For a given classification task the state of the art method fails when the test image is out of classes on which the classifier is trained. 

**Jerry** :How is the model failing?

**Tom**: The failure is in the form of high confidence prediction. High confident prediction means that the margin of error is generally high. Now this scenario is very bad for certain kind of problems that require precise answers like in the field of medical domain and autonomous driving, erroneous answers in the field have very huge impact on life.

**Jerry** :How are these high confidence predictions produced by the model?

**Tom** :These high confidence predictions are produced by the softmax function. The Softmax is computed with the exponential probabilities. The softmax function is given by $$\frac{e^{x_i}}{\sum_{i=1}^{N} e^{x_i}}$$. Small changes in logits would mean that there are bigger changes in the output. 

**Jerry** : Oh that sounds bad. How to solve this issue?

**Tom** : This issue is called detecting out of distribution. The Out of distribution samples tend to have lower softmax values compared to in-distribution (training) samples when passed through a NN