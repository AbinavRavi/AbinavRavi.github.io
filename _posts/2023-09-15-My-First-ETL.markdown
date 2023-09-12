---
layout: post
title:  "My first Prefect ETL Pipeline"
date:   2023-09-10 00:45:00 +0100
comments: True
share: True
categories: Engineering
---
## Problem Statement

There is a business case where the organization is dependent on an API to fetch the data and luckily the data can be stored and used for downstream analytics later. This API costs a lot and the data also needs to be stored securely. But the idea is to not write a script which is put together of all the API calls panda conversions etc that will fail on the drop of a hat because it is meant as a one time usage

## Requirements

The script should 
- re runnable
- configurable 
- fast velocity of development
- easy to maintain.

## Tasks

1. Create a function that fetches the data from the API
2. Convert the API response into a dataframe
2. Store the dataframe in a database
3. Create a pipeline that does this in a sequence.

## Solution
We are going to build the entire thing using prefect and python. I tried my hand at airflow but it just seemed so complex with binaries etc that prefect documentation seemed like a breeze. 

### 0. Install prefect
Install this inside a vitual environment

```
pip install -U prefect
```

## Code snippets
### 1. Create a function that fetches data from API

Since the API call that I have to make is a post API call, the input data to be sent in the request is stored as a modifiable content in a json and then loaded during the task phase. 

