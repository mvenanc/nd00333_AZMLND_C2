# Optimizing an ML Pipeline in Azure

## Overview

This project is part of the Udacity Azure ML Nanodegree.
In this project we demonstrated two possibilities of Azure Machine Learning. We have used Automated ML through the Azure Machine Learning Studio to upload a dataset and set up a Automated ML run using purely the UI which is more user friendly. We run all the steps necessary to set up the project, publish and consume the model.

In the second approach, it was created a pipeline using Azure Machine Learning. For this purpose, it was used Azure Machine Learning SDK to set all the parameters necessary to run the model, set everything such, objective column, metrics, environment settings and so on. In the end the pipeline has been published as well.

The published pipeline can be used by another pipeline or projects. A pipeline is a set of steps which may include data preparation, featurezation, training, deploy, tests, in summary.
all that is need in a ML project. The good thing so, is that pipelines can be reusable. This is different from a Automated ML Project, which can be a part of Pipeline.

## Architecture

The architecture of the project is based on the Azure ML MLOps architecture. There are steps for data preparation, training, validation, deploy and validation the model.

![](images/entire_pipeline.png?raw=true)

The Train Model step presented in the architecture flow above, basically can be summarized in a process that is presented in the next flow below. Since the data is ready to be submitted to a machine learning algorithm, then, there are some steps in order to train and choose the best model to deploy, and then monitor.

![](images/training_model.png?raw=true)

## Project future improvements

As future improvements, There is a chance to improve the model quality by investing time to investigate all the features and run some descriptive statistics analysis in order to find out how important are all the features. Try to select the best ones, as well create another feature. 

Also, a more detailed Automated ML can be run testing many more scenarios and also Deep Learning algorithms in attempt to find the best model.

New models can be compared. Different parameters can be tested using the hyperdrive and than, finding the best model and best parameters that generated the best possible model.

## Screenshots

### Step 2.1 - Registered Datasets

In the image below presents the screen where we can visualize all the datasets that are registered in the Azure Machine Learning Studio. 

To run any machine learning project using Azure ML Studio, is necessary to, first, register the dataset.This is a great feature of Azure ML because using this approach it is possible to version datasets. If, for some reason, a new version of the dataset is released and then updated through the Azure ML Studio, a new version is going to be registered. This feature can help in future debugs or throwback that may occur. Also, 
this feature can help with data governance. 

![](images/step_2_1_registered_datasets_20210123.jpg?raw=true)


### Step 2.2 - Experiment Completed

This image below shows the screen of the Experiment completion. We can see that there are several details of the training run.

The Details shows some properties, such as, the name of the dataset used as input, the duration time of the automated ml training, the best algorithm that was chosen and so on.

All the details presented in this screen is related to the Experiment. Then, there is a way to check all the models that was run and compared in order to choose the best one. This visualization and details can be reached by clicking on the Models tab.

![](images/step_2_2_experiment_completed_20210123.jpg?raw=true)


### Step 3 - Best model
When selection the best model, it is possible to check the its details. Below we can see the details of Voting Ensemble approach.

We can see the main Metrics of the model, as well, details like creation date, compute target, run id, and so on. 

As well, if the feature to run the model explanation was set during the configuration of automated ML run, then is possible to see the Explanations of the model by clicking on Explanations tab. 

There is also a possibility to check the Model outputs. The outputs hold all the outputs of the model, such as model.pkl and files that are used to deploy the model.

![](images/step_2_3_best_model_20210123.jpg?raw=true)


### Step 4.1 - Application Insights
After the model deployment, there is a screen where we can check the endpoint healthy and details. This screen is shown below.

We can check the Rest endpoint where the model was deployed. We can see as well as the computer type, which can be ACI or AKS. 

Another important point to stress is that is possible to obtain the swagger.json wich can be used to deploy the swagger entry for the model deployed.

Another important feature is the Application Insights url. The application insights present a way to monitor de endpoint. By this service, it is possible to have metrics for the endpoints that shows important things like the availability of the endpoint service, accessibility metrics, and much more. 

![](images/step_4_1_application_insights_enabled_20210123.jpg?raw=true)


### Step 4.2 - Logs

The example below shows how to get logs of a deployed model Web service.

![](images/step_4_2_logs_20210123.jpg?raw=true)


### Step 5 - Swagger

Going further to check the model endpoint, it is possible to download de swagger.json and then host an entry point the endpoint configuration in a Swagger environment.

This helps to check all the endpoint entries as well as example of how to call the endpoint. 

![](images/step_5_1_swagger_20210123.jpg?raw=true)


### Step 6 - Benchmark

Using apache tools it is possible to run benchmarks triggering the model endpoint. This approach is helpful to check the endpoint response and latency.

![](images/step_6_1_benchmark_20210123.jpg?raw=true)


### Step 7.1 - Pipeline Created

Now, the image below shows Runs. There is a specific run that was triggered by a pipeline. Pipelines are composed by steps.Each step of the pipeline can perform some work over data, model training, deployment and so on. An automated ml step can be a composition of a pipeline. 
For instance, a pipeline can have a step to clean the data, normalize the data, split the data and then run automated ml. 

![](images/step_7_1_pipeline_created_20210123.jpg?raw=true)


### Step 7.2 - Pipeline Endpoint

Below we can see that a pipeline also can be published as an endpoint. With the pipeline endpoint up and running, it is possible to trigger the pipeline any time.
We want as soon as another job need. This is helpful, because we can create a customized pipeline that can be used by another job which shares common steps.

![](images/step_7_2_pipeline_endpoint_20210123.jpg?raw=true)


### Step 7.3 - Dataset with Automl Module

The pipeline below was created through the SDK. We can see that there is a step to get the data, and then submit this dataset to an automl_module. This pipeline is very small but is possible to see through the Graph how each step is connected.

![](images/step_7_3_dataset_with_automl_module_20210123.jpg?raw=true)


### Step 7.4 - Published Pipeline overview

After the pipeline is published, we can see the details. There is much information, and the most important is the REST endpoint link. This link can be callable.
When this endpoint is triggered, the pipeline will run each step again.

![](images/step_7_4_published_pipeline_overview_20210123.jpg?raw=true)


### Step 7.5 - Pipeline Run Details

The code below uses the sdk to interact with the azure machine learning environment. In details, the code below shows how to get Run details of an Experiment submitted to the Azure Machine Learning.

![](images/step_7_5_run_details_20210123.jpg?raw=true)


### Step 7.6 - Scheduled Run

Below is present an overview of each Run submitted to Azure Machine Learning. Each experiment is composed by Runs. Each Run can be viewed through the ui.

This screen shows some important information, such as, Run status, graphs of metrics comparison and so on.

![](images/step_7_6_scheduled_run_20210123.jpg?raw=true)


## Screencast vídeo (Clik on the image - The video is hosted on youtube)

[![Watch the video](https://img.youtube.com/vi/Y6nTz96Xqso/maxresdefault.jpg)](https://youtu.be/Y6nTz96Xqso)

