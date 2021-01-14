# Operationalizing Machine Learning

This is the second project of Udacity Machine Learning Engineer with Microsoft Azure Nanodegree Program. In this project we are trying to build deploy a model that is used to predict whether a client will accept a term deposit or not based on the direct marketing campaigns of a company. Using Azure and its workspace, this project looks at creating a cloud based machine learning model, from building, deployment to consumption and finally publication. It begins with uploading the dataset and using the AutoML function on Azure to generate the best model using a metric and ending criteria. The model is then deployed using Azure ACI which generates a swagger URI and REST API endpoint. It also streamlines the entire flow using a pipeline.

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step.

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

### Step 4: Enable Logging

### Step 5: Swagger Documentation

### Step 6: Consume Model Endpoints

### Step 7: Create, Publish and Consume a Pipeline

*TODO*: Write a short discription of the key steps. Remeber to include all the screencasts required to demonstrate key steps. 

*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.

## Improvements and Future Work

- K-Fold cross validation techniques with deep learning enbled can be set in the AutoML configuration to get better accuracy.
- The swagger json file can be modified to include additional information about the model in real time for datasets that are updated constantly and not uploaded.
- Comparing the model results with a hyperdrive configuration to see what parameters are better at predicting the output column values.
- Generating more features from the dataset columns to make the models more open ended.

## Screen Recording
https://youtu.be/bA6-QFxK0Bw
