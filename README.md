# GitHub actions and repository environments

## Background
This repository demonstrate how to run a github action against multiple repository environments in which some of those environments need approval before deploying to the environment

Since this is a proof of concept project, the action does not deploy code to any servers but instead print the environment name at the end.

## Enviironments
I defined 3 environments 

| Environment Name | Need approval |
| -- | -- |
| DEV | ❌ |
| QA | ✅ |
| PROD | ✅ |


## Action
This action package a Java based application and accepts environment name as input parameter. Action file is located in `.github/workflows/environment-based.yml`

## Creating environments

You need to have admin access to the repository. To create a new environment you can got to `Repository settings -> Environments -> click on new Environment` 
