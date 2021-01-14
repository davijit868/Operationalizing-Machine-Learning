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

An AutoML experiment has been created to model the data as classication task.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_2.png)

AutoML produced the best model i.e. VotingEnsemble with 91.9% accurcy.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_3.png)

### Step 3: Deploy the Best Model

The best model achived by AutoML has been deployed using Azure Container Instances with key-based authentication enbled

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_4.png)

### Step 4: Enable Logging

Logging has been enabled for the endpoint using log.py script. 

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_5.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

### Step 5: Swagger Documentation

swagger.json file is downloaded and kept in the same directory(swagger) as swagger.sh and server.py. Then swagger.sh file is executed which runs swagger ui as local containerrized application, after that server.py is executed which creates a python local server.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

### Step 6: Consume Model Endpoints

Model enpoints are consumed using endpoint.py script which sends sample data for prediction and the output is received in console as JSON payload.

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

### Step 7: Create, Publish and Consume a Pipeline

Please find the below screenshots which describes the creation, publication and consumption of pipeline using aml-pipelines-with-automated-machine-learning-step.ipynb

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

![alt text](https://github.com/davijit868/Operationalizing-Machine-Learning/blob/master/Screenshoots/screenshot_6.png)

## Improvements and Future Work

- K-Fold cross validation techniques with deep learning enbled can be set in the AutoML configuration to get better accuracy.
- The swagger json file can be modified to include additional information about the model in real time for datasets that are updated constantly and not uploaded.
- Comparing the model results with a hyperdrive configuration to see what parameters are better at predicting the output column values.
- Generating more features from the dataset columns to make the models more open ended.

## Screen Recording
https://youtu.be/bA6-QFxK0Bw
