---
layout: post
title:  "Private Python packages on Github and Gitlab"
date:   2023-02-20 00:45:00 +0100
comments: True
share: True
categories: Engineering
---

If we work in an industry setting we need private packages for using as libraries to share across teams working on same project. To do that we can use package registry in github and gitlab. 

## GitLab

### Requirements

* A deploy token pair with username and deploy key from gitlab repository
* A repository for this purpose
* poetry package management

### Steps

1. Create a repository with the name of the package and then put all the code inside the repository
2. Create a ```__init__.py``` file  inside the repository and import all the classes and functions that needs to be exposed to users of the package
3. ```pip install poetry``` to install poetry in the virtual environment
4. Import the dependencies for the package by using ```poetry add <package name>```
5. To ensure that package is maintained properly write tests to keep tabs on functionality
6. Once everything is done then run the following three commands in sequence to build and push the package to gitlab repository
    - ```poetry config repositories.<variable_name> https://gitlab.com/api/v4/projects/<project_id>/packages/pypi```
    - ```poetry build```
    - ```poetry publish --repository <variable_name> -u <gitlab_deploy_token_name> -p <gitlab_deploy_token>```

Now the pypi package is available for internal usage and can be installed by 
 * ```pip install <package_name> --no-deps --index-url https://<gitlab_deploy_token_name>:<gitlab_deploy_token>@gitlab.example.com/api/v4/projects/<project_id>/packages/pypi/simple```

## GitHub 
I would like to thank my friend Abhijeet Parida for providing a template with a very beautiful readme to accomplish this task in [Github](https://github.com/a-parida12/poetry_pypi_template)

## Extensions
Ideally should use a ci pipeline to create the packages so that there can be a versioning that can be automatically done

## References

1. https://docs.gitlab.com/ee/user/packages/pypi_repository/
2. https://docs.mpcdf.mpg.de/doc/data/gitlab/devop-tutorial.html
3. https://github.com/a-parida12/poetry_pypi_template