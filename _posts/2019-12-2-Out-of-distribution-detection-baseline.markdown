---
layout: post
title:  "Baseline for Out of Distribution Detection"
date:   2019-12-07 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---

This is the first paper in a series of Out of distribution detection literature. In the coming weeks I will be reviewing one paper each week. 

#### Introduction:
A Neural network trains on a given set of data and during deployment(test time) it is unrealistic to expect the same distribution from the test data as well. For a given classification task the state of the art method fails when the test image is out of classes on which the classifier is trained. 

How is the failure?
The failure is in the form of high confidence prediction. High confident prediction means that the margin 