# Serverless hello world
This is an example hello world api created with the serverless framework that runs on AWS Lambda. 


## Prerequisites 

* You have AWS Access keys 
* `cp aws-secrets.example aws-secrets`
* `source aws-secrets`


## Deploy 

* `serverless deploy -v`


## Test 

Now you could invoke the Lambda with `serverless invoke -f hello -l` if everything went fine


## Undeploy

* `serverless remove`


## Create API Gateway 

Now you have deployed your lambda and can invoke it via serverless. But you may want call it like a 'real' REST API, so we need to place an API Gateway which calls our Lambda Function. 

* The Swagger API definition can be found [here](api-definition.yml)
* Go to the API Gateway section in the AWS console UI and create a new API Gateway with the API definition. 
* After that you need to specify an action for the hello endpoint, where you select the deployed Lambda. 
* Now you could test the API via UI in order to see if everything works fine
* Deploy the API with the 'Actions' Dropdown box and create a stage on the way 


## Test the Gateway

For testing the API I recomment using Postman because of the way you have authorize your request which is pretty convenient using Postman. 

* Choose AWS Signature for authorization method 
* Fill in your Access and Secret key as well as the region your user
* You can grab the API Gateway URL by clicking on the created stage
* Fire your request and you should get a response 




