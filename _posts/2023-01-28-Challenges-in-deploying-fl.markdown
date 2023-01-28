---
layout: post
title:  "Challenges in Deploying Federated Learning Models"
date:   2023-01-28 18:45:00 +0100
comments: True
share: True
categories: Machine learning
---

 # Difference between Federated learning and Normal Machine learning
In normal machine Learning the data resides in a single source or is aggregated into a single source by certain ETL (extract, load and transform operations) by data engineers from multiple databases and then used to train a machine learning model.

In Federated learning the data doesn't leave the source of origin. There is a central server which is owned by Data scientists and the data sources are considered clients. Machine learning is done by decentralized communication and collecting only relevant model updates in the central server.


![Conventional Machine learning workflow Image Source](https://deepai.org/publication/two-stage-optimization-for-machine-learning-workflow)

![Federated Learning Image Source](https://federated.fastforwardlabs.com/)
## Advantages of Federated learning
Federated learning can be used when data are locked due to several factors such as compliance, location, regulation etc. To do Machine learning on such data in a normal setting is not possible as the data cannot leave the source and distributed training with preserving privacy becomes an advantage in the favour of using Machine learning.

## Use cases of Federated Learning
This above-mentioned advantages lead us to think about various use-cases in the field of

Healthcare
Insurance
Fintech
IoT
Industries for doing predictive maintenance
In all of the above cases there is a need for privacy and getting the data out of the source can be very cumbersome.

## Problem with deploying Federated Learning
Federated Learning in Google board is a good example of how it is being deployed in the real world. However, there is a difference between the Google board use-case and the use-cases mentioned above.

The difference lies in the ownership of the source data. In most of the general cases where privacy is required the ownership differs from the person performing machine learning on the data.

This means that a part of the machine learning pipeline which is cleaning of the data and selecting the features needs to be done on the data owner side before allowing the learner to create a model on the data. This involves the separation of responsibility between the two sides.

The above situation is very similar to a front-end engineer and back-end engineer when they don't have a common API specification to talk to each other. In Machine learning feature engineering and exploratory data analysis help in the understanding of the data. With just selected features being available to the learner it becomes very difficult to understand what those features are and how an efficient model can be made.

Problems can also arise during communication and this may cause incorrect data to be sent to learn. The cost is also high compared to normal machine learning as two individual people with specific skills are required to complete the task at hand.

## How to solve this issue?
The issue can be solved by both parties coming together and deciding on a general type specification on how the data should look like and what would be the necessary features (Again may be quite unproductive since there is the cost of two people involved). But that is the best possible solution as of now

### Use-cases where ownership of data remains the same
However, the above issue will not exist in use-cases where the data collection is being done by an application which is being deployed by the owner of the server. When the application inputs and outputs are defined the data is generally of a certain structure and it is easy to run federated learning and deploy it with ease.

### Data Standard specification
The other way of solving the communication issue is setting of a standard specification for different data types (tabular, image, text, audio) imposing requirements of certain fields can solve the communication problem.