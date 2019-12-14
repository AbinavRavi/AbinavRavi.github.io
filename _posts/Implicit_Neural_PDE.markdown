---
layout: post
title:  "Implicit Neural Solver for time dependent PDE for Convergence Guarantee"
date:   2019-12-07 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---

This week's paper on discussion is my own NeurIPS workshop paper on [Implicit Neural Solver for Time-dependent Linear
PDEs with Convergence Guarantee](https://arxiv.org/abs/1910.03452) published at workshop [Machine learning with guarantees](https://sites.google.com/view/mlwithguarantees)

This conversation is between me and my friends explaining the paper to them.

**Friend**: Hey I heard about your paper, Could you explain what you do in that?

**Me**: Of Course, We have partial differential equations which describe different physical phenomenon. Now solving these partial differential equation analytically is very difficult and there have been many numerical techniques to solve the stuff on a computer. (Interesting fact is that the very famous Navier stokes equation which is used to simulate fluid behaviour is one of the [millenium problems](https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness).) Now the basic idea is to develop a neural network solver that can identify discretization scheme by itself. 

**Friend** But the current existing solvers and discretization choosing works well why introduce something complicated?

**Me**: The general idea is to learn from simulated data and instead of choosing the discretization method yourself the network does it for you. We also did some proofs on theoretical correctness of the idea of using neural networks and found that the neural solver is actually quite fast than a normal solver. So we plan to save time too.

**Friend** : 

**Me**: 