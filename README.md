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

- You need to have admin access to the repository. To create a new environment you can got to `Repository settings -> Environments -> click on new Environment`
- The enter environment name and click on configure environment button
- 

![image](https://user-images.githubusercontent.com/90400593/188016214-d8c23159-907c-424b-b3ba-7644bae2570b.png)
![image](https://user-images.githubusercontent.com/90400593/188016337-7005314c-6bdf-49c2-a926-d9ed936b53fe.png)

### Environments

### DEV
![image](https://user-images.githubusercontent.com/90400593/188016685-e33057f1-d1c0-4107-8a37-42de44473ce7.png)
### QA and PROD with approver needs
Click on environment name then enable `Required reviewers` then in the search box type github handles and add desired reviewers
![image](https://user-images.githubusercontent.com/90400593/188016975-a8d1feac-2c2c-4968-8d7f-6083b4f343e1.png)

Click on environment name then enable `Required reviewers` then in the search box type github handles and add desired reviewers

## Trigger actions

### Against environment
Go to `Actions tab -> select the action from side menu -> click on Run workflow -> select environment -> click on run workflow green button`

### DEV
Since there is no reviewer required, it automatically starts and finishes the run and look into `build and deploy summary`
![image](https://user-images.githubusercontent.com/90400593/188017846-4b2e5bc7-fb5c-477e-abc8-e6f8c98fbce9.png)

### QA and PROD
This step needs approval and when you trigger the action, it sends an approval request to reviewer (usually via email, it depends on your github notification settings)
In action run details page click on `review deployment (if you are a reviewer) -> select the environment name in poped up window -> leave a comment if you want -> approve or reject the request`

If you approve the request then action will be triggered and if you reject it then action's run will be cancelled.

You will see a `Deployment reviews` box below action run

![image](https://user-images.githubusercontent.com/90400593/188018132-ff51b47c-54cd-49a7-af5f-696d2de4d433.png)
![image](https://user-images.githubusercontent.com/90400593/188018157-e7609f4f-bd81-4085-85d5-76e4ea530625.png)
![image](https://user-images.githubusercontent.com/90400593/188018353-ddc6fdf3-16b8-422e-8586-2350e528a155.png)
![image](https://user-images.githubusercontent.com/90400593/188018759-e0006236-fcdf-4d4e-9435-f588c7fd2912.png)



