---
layout: post
title:  "ODIN and Generalized ODIN"
date:   2020-05-01 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---

This post will deal with advanced version and a comparison with this [post](https://abinavravi.github.io/machine/learning/2019/12/07/Out-of-distribution-detection-baseline.html)

**Tom**: Hey let us talk about a new paper called [ODIN](https://arxiv.org/abs/1706.02690) that improves our baseline for Out of distribution detection paper and a paper that tries to generalize the ODIN paper called [Generalized ODIN](https://arxiv.org/abs/2002.11297).

**Jerry**: How does this paper improve the baseline method?

**Tom**: In this paper they consider the Softmax score as the confidence score as like in baseline but make small changes to the input by perturbing it. They also use temperature scaling to increase the gap between In distribution and Out of Distribution.

**Jerry**: That sounds simple and elegant but can you tell me what is temperature scaling?

**Tom**: Temperature scaling is when a single scalar hyperparameter T is used to increase the entropy of the given logit. By choosing this hyperparameter very carefully we can push the softmax scores of In and OOD samples further apart thereby making it very distinguishable.
Mathematically we can represent the softmax score with Temperature scaling as 

$$ S_i(x;T) = \frac{\exp(f_i(x)/T)}{\sum\limits_{j=1}^N \exp(f_j(x)/T)} $$

**Jerry**: Can you tell more about the Input Preprocessing that you were talking about?

**Tom**: The input preprocessing is simple. inspired by goodfellow in this [paper](https://arxiv.org/abs/1412.6572) the input is perturbed a little. This is given by $$ \tilde{x} = x - \eps sign(-\nabla_x log S_{\hat{y}}(x;T))$$