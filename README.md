

**Operationalizing Machine Learning**

In this project, we have used the Bank Marketing dataset to train a machine learning model using AutoML feature of Azure Machine Learning Studio.  We will then later configure it for pipeline production.  We will host it in an Azure Container Instance and later test it using REST endpoints. 

**Architecture Overview**

Below is a high-level diagram of the architecture used for this project.  

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image1.png"> </img>
           

These are the steps that are going to go through to complete the operational objectives of the lab.

1. Specify and upload the marketing dataset
2. Configure the AutoML run 
3. Determine and deploy the best model to REST endpoint
4. Enable logging and application insights. Logging allows us to address performance issues
5. REST endpoint testing utilizing Python script.  We use JSON payload to test and consume the endpoint.
6. We use Python SDK to create a pipeline and publish it 

**Ways to Improve the project** 



1. Create a frontend to allow interaction with the endpoints that would allow better interaction then command-line script
2. Review logs and application insights to see performance and refine the application. 

**Key Steps** 

<span style="text-decoration:underline;">Authentication</span>

	Not required because using Udacity Lab 


## <span style="text-decoration:underline;">Automated ML Experiment</span>

We download and register the dataset so that we can setup and run AutoML.

**Registered Datasets**

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image2.png"> </img>


Next, we configure and run our AutoML.  Once the run is completed we will be able to select the best model and publish it to make it available via REST endpoint. 

Run Completed 

Once the run is complete we can view the models and their relative accuracy in the grid.

The below images shows the dataset used, the completion status of the experiment, and the different models generated by AutoML. We can also notice that the best model generated is votingensemble model with an approximate accuracy of about 92%


<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image3.png"> </img>



AutoML Best Model Explanation. 


<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image4.png"> </img>


<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image5.png"> </img>

Step 3 

Deploy Model.

In this step, we take the most accurate model and make it available to a secured REST endpoint that we will later consume with a Python script.   We also enable application insights on the endpoint so that we can observe performance and errors that might be encountered by end users.

Deployed endpoint details 

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image6.png"> </img>

Show application insights enabled 

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image7.png"> </img>

Logging turned on 

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image8.png"> </img>

**Swagger**

In this step, we will use swagger to interact with the endpoint.  Swagger allows us to document the endpoint and show a template that can be used to make REST calls to the endpoint. 

Azure provides a swagger.json automatically that is used by the swagger container to produce a website that documents the HTTP endpoint for a deployed model.


<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image9.png"> </img>


Endpoint JSON payload** **

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image10.png"> </img>


We use the provided Python script to consume the endpoint.  The script was slightly modified to include the url and key for our new endpoint. The screen shot below shows the response from the endpoint. 

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image11.png"> </img>


**Pipeline Creation and Deployment**

In this step, we have used python SDK to create and publish the pipeline.  This allows us to make the pipeline process repeatable and operationalizes the pipeline process.

We can see that:



*   Pipeline scheduled run details
*   Pipeline has been successfully created
*   Pipeline REST endpoint in an active state
*   Pipeline step details


<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image12.png"> </img>

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image13.png"> </img>

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image14.png"> </img>

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image15.png"> </img>

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image16.png"> </img>

<img src = "https://github.com/slcdlvpr/mlpipeline3/blob/main/Images/image17.png"> </img>


**Screen Recording **

**[https://vimeo.com/556066677/99cabdb63d](https://vimeo.com/556066677/99cabdb63d) **
