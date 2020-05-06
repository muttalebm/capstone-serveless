[![Build Status](https://travis-ci.org/muttalebm/capstone-serveless.svg?branch=master)](https://travis-ci.org/muttalebm/capstone-serveless)
# Serverless TODO

This repo implements a simple TODO application using AWS Lambda and Serverless framework.

There are two components of the Project
 - Backend 
 - Client 

# Functionality of the application

This application will allow creating/removing/updating/fetching TODO items. Each TODO item can optionally have an attachment image. Each user only has access to TODO items that he/she has created.

# Backend
The `backend` folder contains the AWS lamda functions which provide the Serverless Todo API. 

It is built and deployed to AWS using TravisCI on each push to master/dev/test branches

`.travis.yml` is located at the root of the project

## Endpoints:
  * GET - https://{{apiid}}.execute-api.us-east-1.amazonaws.com/prod/todos
  * POST - https://{{apiid}}.execute-api.us-east-1.amazonaws.com/prod/todos
  * PATCH - https://{{apiid}}.execute-api.us-east-1.amazonaws.com/prod/todos/{todoId}
  * DELETE - https://{{apiid}}.execute-api.us-east-1.amazonaws.com/prod/todos/{todoId}
  * POST - https://{{apiid}}.execute-api.us-east-1.amazonaws.com/prod/todos/{todoId}/attachment

# Frontend

The `client` folder contains a web application that can uses the API for Serverless Todo.

The frontend is deployed to and hosted at AWS S3 using Jenkins.
The `Jenkinsfile` is located at the project root. 
This can be configured to be built and deployed on each commit/ pull request using github hooks.

Application URL: http://capstone-serverless-todo-dev.s3-website-us-east-1.amazonaws.com/

## Authentication

We used auth0 service for authentication



# How to run the application

## Backend

To deploy an application run the following commands:

```
cd backend
npm install
sls deploy -v
```

## Frontend

To run a client application first edit the `client/src/config.ts` file to set correct parameters. And then run the following commands:

```
cd client
npm install
npm run start
```

This should start a development server with the React application that will interact with the serverless TODO application.

# Postman collection

An alternative way to test your API, you can use the Postman collection that contains sample requests. You can find a Postman collection in this project. To import this collection, do the following.

Click on the import button:

![Alt text](images/import-collection-1.png?raw=true "Image 1")


Click on the "Choose Files":

![Alt text](images/import-collection-2.png?raw=true "Image 2")


Select a file to import:

![Alt text](images/import-collection-3.png?raw=true "Image 3")


Right click on the imported collection to set variables for the collection:

![Alt text](images/import-collection-4.png?raw=true "Image 4")

Provide variables for the collection (similarly to how this was done in the course):

![Alt text](images/import-collection-5.png?raw=true "Image 5")
