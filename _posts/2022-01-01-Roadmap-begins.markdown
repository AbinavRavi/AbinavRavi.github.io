---
layout: post
title:  "The Roadmap Begins"
date:   2022-01-01 18:45:00 +0100
comments: True
share: True
categories: Engineering
---

Over the past year in my job I learnt a lot in my job as a data scientist at deepc gmbh. Some of which I have tried to generalise and document in the coming series. Please find the list of posts and topics in the roadmap below

![Roadmap](</ml/Series1/Blog_Series_1.jpg>)

The idea is to take a model to production quality. This is a general outline of the process of making a model into a microservice. 

The post will be starting from
1. Structuring the repository with certain elements like linting, pre-commit etc
2. unit testing of Model inference and adding coverage.
3. Writing a web-endpoint with flask or fast-api
4. Adding ci.yml file and makefile to run multiple commands from continuous integration
5. Dockerizing the Application with the inference as endpoint
6. Deploying using kubernetes and Documentation of the microservice. 

Please feel free to comment. 