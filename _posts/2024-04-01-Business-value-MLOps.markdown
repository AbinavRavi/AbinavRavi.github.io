---
layout: post
title:  "Structuring ML applications to deliver business value - MLOps Maturity model"
date:   2024-04-10 12:45:00 +0530
comments: True
share: True
categories: Machine learning Operations
---

If you also want AI systems to deliver business value, you have come to the right place. To deliver proper business value there needs to be a deep understanding of how to create reliable systems that can consistently deliver. Having a couple of machine learning models that don't do well in production doesn't help. 

In this post, we will talk about how to technically design a system that can deliver business value using machine learning effectively. This is inspired by various MLOps podcasts and talks on the internet. 

## Maturity of Machine Learning 

To deliver value there is a need to understand where we stand and what we need to provide. There are multiple models of the Machine Learning Operations cycle that can help us understand this scenario. Out of the different maturity models, the Azure MLops maturity model has a complete understanding of the various components that constitute them. 
Since we are mostly concerned with designing machine learning systems in this post the emphasis from the Azure model is on the Model creation, Model release and application integration phase. The organization aspect of things isn't covered in this post but is also a main pillar to ensure that there are teams of different strengths coming together to build a reliable system.

Most teams start with the data scientist having a model built on the business case and then waiting for engineers to deploy this to production.
 
## Stages of Machine Learning deployment
### Minimum Deployable Product:
In order to bring machine learning models to production these are minimum features that it must have to function in a semi automatic way and deliver some business value in a quick iteration. It is important to understand that this is the baseline in terms of value creation and the other stages explained below are important to have a reliable machine learning system that can deliver consistent value without manual intervention. 

We would have a machine learning model at this point in time this can be stored at a cloud storage location or at the server. The first step is to wrap an API with endpoints that can take requests and can then return an inference value of some meaning. 

For example if the problem is a classification problem just returning a vector of 0 and 1 makes no sense to the end user. This API would do the conversion to possible categories and return value to the user that can be displayed. 
There must be some semblance of testing suite that must be present in the repository that checks if the model artifact is being downloaded or not (whether location on cloud has changed or not). Then 

### Automatic Retraining

### Complete Automatic Machine Learning pipeline