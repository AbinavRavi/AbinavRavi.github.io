---
layout: post
title:  "A simple Unified framework for detecting OOD Samples"
date:   2020-1-5 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---

**Tom**: Hey jerry, remember a couple of weeks ago I told you about a baseline detector for Out of distribution sample detection. I just read a paper that tops off the idea with better techniques.

**Jerry**: Is it so. I was thinking about it and thought that there should be better approach. Are you talking about [A simple unified framework for detecting Out of Distribution samples and Adversarial attacks](https://arxiv.org/abs/1807.03888).

**Tom**: No but carry on I haven't heard about this one yet

**Jerry**: This paper is quite sleek that it provides a confidence score based on mahalanobis distance and can be used in a bayesian manner and also for pretrained networks.

**Tom**: A confidence score! That introduces the concept of uncertainty in the network right?

**Jerry**: Yes of course. Let me explain in detail. In a bayesian framework the previous baseline paper the usage of softmax would be similar to using confidence from a posterior distribution $$(p(y;\middle|;x))$$. In this papers the authors propose the usage of generative classifier based technique to measure probability density of test sample in feature space.

**Tom**: Could you please explain what is this generative classifier?

**Jerry**: That is a good question very essential for understanding this paper. In simpler terms the aim of a generative classifier is to learn about the joint distribution $$p(x,y)$$ and then using bayes rule to estimate the posterior prediction.

**Tom**: So where do we use the generative classifier?

**Jerry**: After training a network or having a pretrained network we assume that the class conditional distribution $$ p(f(x)\midy)$$ or the training is following a Gaussian distribution. Which means that during the training the data takes the distribution of Normal distribution (Yes the bell curve one, Statisticians and Data scientists like it very much). Now this can be mathematically written as 
$$ P(f(x);\mid;y=c) = \mathcal{N}(f(x)\mid\mu_c,\Sigma)$$

**Tom**: Are there any more assumptions?(sarcastically)

**Jerry**: The main idea is getting the theoretical link between Gaussian discriminant analysis(GDA) and softmax classifier. The posterior defined by generative classifier under GDA is equal to softmax classifier.

**Tom**: Ah okay, I guess now they just take the statistical parameters. But I am not so sure can you answer in affirmative?

**Jerry**: I can, for estimating the parameters of the generative classifier from the softmax classifier that we have they calculate the mean and covariance of training samples

mathematically it is given as
$$ \widehat{\mu_c} = \frac{1}{N_c} \sum\limits_{i:y_i=c} f(x_i) , \widehat{\Sigma} = \frac{1}{N} \sum\limits_{c}\sum\limits_{i:y_i=c} (f(x_i) - \widehat{\mu_c})(f(x_i) - \widehat{\mu_c})^T $$

**Tom**: You were telling about a confidence score but till now I don't hear a mention of it.

**Jerry**: The next step is calculating confidence