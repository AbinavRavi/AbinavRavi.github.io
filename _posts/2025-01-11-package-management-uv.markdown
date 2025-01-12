---
layout: post
title:  "Python Package management with uv"
date:   2024-01-13 12:45:00 +0530
comments: True
share: True
categories: Programming
---
# Background 

Working as a Machine learning Engineer who deploys most of the stuff on the web downloading dependencies become a bottleneck at some point in time. When I started working we were using requirements.txt with versions and this was a britte setup where if by accident a version number could be changed unintentionally everything could cause issues, how to resolve this issue is when pyenv came but usability was a slight concern, then came poetry which I had been using for about 3.5 years. What was the problem that poetry solved

It came with a lock file which could be regenerated if something went wrong a pyproject.toml file which where multiple configurations could be set and modified, but with time generating the lock file and just doing poetry install seemed a bit slow as poetry is a project that is written completely in python and that meant the GIL was a limiting factor. 

With PyO3 and rust bindings for python came a set of python packages which outsourced the major processing to rust and pydantic is one of the libraries that took this by rewriting their entire core library in rust and bringing some breaking changes with pydantic v2.0. So it was only a matter of time before package managers were also rewritten in rust. While the environment was right came out uv from astral which had some success stories of writing some key pythonic linting software such as ruff. 

# What is uv?

uv is basically a drop in replacement for poetry and is incredibly fast. The documentation at uv says that it might be 10-100x faster. From anecdotal evidence it reduced our build times especially requirements installation by atleast 2-3x. 

# How to use uv?

## Installation

Follow this [documentation](https://docs.astral.sh/uv/getting-started/installation/) to install the uv according to your operating system

## Project usage
A new project can be created with `uv init` if the repo already exists or if the repo doesnt exist then you can create a new project with `uv init <reponame>`. There are two types of projects that can be created 

1. applications
2. Libraries

a `uv init` creates an application project by default and we have use `uv init --lib` for the library project. 

with project creation the following files are created

* pyproject.toml
* .python-version
* README.md
* hello.py 

if the code needs to be a python package we can use `uv init --package` to create the corresponding build system and utils in pyproject.toml.

For further information on usage please refer [documentation](https://docs.astral.sh/uv/concepts/projects/init/)

## Adding dependencies


