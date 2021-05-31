

# Operationalizing Machine Learning

In this project, we have used the Bank Marketing dataset to train a machine learning model using AutoML feature of Azure Machine Learning Studio.  We will then later configure it for pipeline production.  We will host it in an Azure Container Instance and later test it using REST endpoints. 

 # Architecture Overview

Below is a high-level diagram of the architecture used for this project.  
![architecture diagram](Images/image1.png) 


           

These are the steps that are going to go through to complete the operational objectives of the lab.

1. Specify and upload the marketing dataset
2. Configure the AutoML run 
3. Determine and deploy the best model to REST endpoint
4. Enable logging and application insights. Logging allows us to address performance issues
5. REST endpoint testing utilizing Python script.  We use JSON payload to test and consume the endpoint.
6. We use Python SDK to create a pipeline and publish it 

# Ways to Improve the project

1. Create a frontend to allow interaction with the endpoints that would allow better interaction then command-line script
2. Review logs and application insights to see performance and refine the application. 

# Key Steps  

<span style="text-decoration:underline;">Authentication</span>

	Not required because using Udacity Lab 


## <span style="text-decoration:underline;">Automated ML Experiment</span>

We download and register the dataset so that we can setup and run AutoML.

# Registered Datasets 

![Registered Datasets](Images/image2.png)



Next, we configure and run our AutoML.  Once the run is completed we will be able to select the best model and publish it to make it available via REST endpoint. 

Run Completed 

Once the run is complete we can view the models and their relative accuracy in the grid.

The below images shows the dataset used, the completion status of the experiment, and the different models generated by AutoML. We can also notice that the best model generated is votingensemble model with an approximate accuracy of about 92%


![Run Completed](Images/Image3.png)



# AutoML Best Model Explanation. 

![AutoML Best](Images/Image4.png)


           
![Model Explanation](Images/Image5.png)



# Deploy Model.

In this step, we take the most accurate model and make it available to a secured REST endpoint that we will later consume with a Python script.   We also enable application insights on the endpoint so that we can observe performance and errors that might be encountered by end users.

Deployed endpoint details 

![endpoint](Images/Image6.png)


# Show application insights enabled 

![application insights](Images/Image7.png)


# Logging turned on 


![Logging](Images/Image8.png)


# Swagger 

In this step, we will use swagger to interact with the endpoint.  Swagger allows us to document the endpoint and show a template that can be used to make REST calls to the endpoint. 

Azure provides a swagger.json automatically that is used by the swagger container to produce a website that documents the HTTP endpoint for a deployed model.

![swagger](Images/Image9.png)


Swagger responses for the model 

![swagger](Images/Image18.JPG)


# Endpoint JSON payload
![payload](Images/Image10.png)


We use the provided Python script to consume the endpoint.  The script was slightly modified to include the url and key for our new endpoint. The screen shot below shows the response from the endpoint. 

![endpoint](Images/Image11.png)



# Pipeline Creation and Deployment 

In this step, we have used python SDK to create and publish the pipeline.  This allows us to make the pipeline process repeatable and operationalizes the pipeline process.

We can see that:

*   Pipeline scheduled run details
*   Pipeline has been successfully created
*   Pipeline REST endpoint in an active state
*   Pipeline step details

![Pipeline](Images/Image12.png)

![Pipeline1](Images/Image131.png)

![Pipeline2](Images/Image141.png)

![Pipeline3](Images/Image15.png)

![Pipeline4](Images/Image16.png)

![Pipeline5](Images/Image17.png)



# Screen Recording

[https://vimeo.com/556066677/99cabdb63d](https://vimeo.com/556066677/99cabdb63d) 
