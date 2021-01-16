# Operationalizing Machine Learning

This is the second project of Udacity Machine Learning Engineer with Microsoft Azure Nanodegree Program. In this project we are trying to build deploy a model that is used to predict whether a client will accept a term deposit or not based on the direct marketing campaigns of a company. Using Azure and its workspace, this project looks at creating a cloud based machine learning model, from building, deployment to consumption and finally publication. It begins with uploading the dataset and using the AutoML function on Azure to generate the best model using a metric and ending criteria. The model is then deployed using Azure ACI which generates a swagger URI and REST API endpoint. It also streamlines the entire flow using a pipeline.

## Architectural Diagram
![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/Architecture.png)

## Key Steps
### Step 1: Authentication

I have used the lab environment provided by Udacity for this project so this step does not apply for my case.

### Step 2: Automated ML Experiment

In this step Bank Marketing Dataset has been registered to Azure Machine Learning Studio from URI.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_1.png)

An AutoML experiment has been created to model the data as classication task. As per the experiment creation process a compute instance has been provisioned and certain other patamer like metrics, maximum execution time etc has been set. 

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_2.png)

AutoML tried a lot of algorithms and produced the best model i.e. VotingEnsemble with 91.9% accuracy within just 30 minutes. 

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_3.png)

### Step 3: Deploy the Best Model

The best model achived by AutoML has been deployed using Azure Container Instances with key-based authentication enbled. The deployment status is heathy which means it is successfully deployed and running.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_4.png)

### Step 4: Enable Logging

Config.json is downloaded from portal which has all the necessary configuration settings. We choose the best model for deployment and enable key based "Authentication" while deploying the model using Azure Container Instance (ACI). The executed code in logs.py enables Application Insights. "Application Insights enabled" is disabled before executing logs.py. We can see the logs in command prompt also using the application insights url provided in the endpoint.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_5.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

### Step 5: Swagger Documentation

swagger.json file is downloaded and kept in the same directory(swagger) as swagger.sh and server.py. Then swagger.sh file is executed which runs swagger ui as local containerized application, after that server.py is executed which creates a python local server. The swagger documentaion generated from JSON file, specific to our endpoint can be seen using the locally hosted swagger ui which documents the score endpoint i.e. input output variables and its format.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_7.png)

### Step 6: Consume Model Endpoints

Deployed model enpoints are consumed using endpoint.py script which sends sample data for prediction and the output is received in console as JSON payload. The endpoint.py script has been updated with the URI for the endpoint and the key for authentication. Using HTTP post method we sent the data to endpoint as JSON body.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_8.png)

### Step 7: Create, Publish and Consume a Pipeline

A AzureML pipeline is created using aml-pipelines-with-automated-machine-learning-step.ipynb notebook, this pipeline helps automate the entire AutoML model building, deployment of best model, creation of enpoint for the deployed model, as well as consumption and publication. The pipeline building process starts with creating a computing instance with a specific number of nodes and running the jupyter notebook on that with the required parameter changed for my specific use case. Please find the below screenshots for those tasks.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_9.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_10.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_11.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_12.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_13.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_14.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_15.png)

## Improvements and Future Work

- K-Fold cross validation techniques with deep learning enbled can be set in the AutoML configuration to get better accuracy.
- The swagger json file can be modified to include additional information about the model in real time for datasets that are updated constantly and not uploaded.
- Comparing the model results with a hyperdrive configuration to see what parameters are better at predicting the output column values.
- Generating more features from the dataset columns to make the models more open ended.

## Screen Recording
https://youtu.be/bA6-QFxK0Bw
