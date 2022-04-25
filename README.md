<h1 align="center">
  <img alt="" src=".github/cover-node.js.png">
  
  <br />

  Ignite Journey
</h1>

<p align="center">
  <img alt="Node.js Logo" src="https://img.shields.io/badge/Node.js-LTS-339933?logo=node.js">&nbsp;&nbsp;
   <img alt="GitHub" src="https://img.shields.io/github/license/lemuelZara/concepts-nodejs.svg">
</p>

<br />

## Chapter VI - Challenge 01 - Building with serverless

In this challenge you will recreate a part of the *todos* API that was developed in the challenge [Conceitos do Node.js](https://www.notion.so/Desafio-01-Conceitos-do-Node-js-59ccb235aecd43a6a06bf09a24e7ede8) but this time the framework should be used [Serverless](https://www.serverless.com/).

<br />

Each functionality must be created in a separate function file according to what was seen in this last module.
The routes that must exist are:


- **POST -** `/createTODO/{userid}`

    This route must receive the `id` of a user by `pathParameters` (you can create this id manually just to fill the field) and the following fields in the body of the request: `title` and `deadline`, where `deadline` is the deadline for the *todo*.

    The *todo* must be saved with the following fields in DynamoDB:

    ```
    { 
    	id: 'uuid', // generated id to guarantee a unique todo with the same id
    	user_id: 'uuid' // userid received in pathParameters
    	title: 'Task title',
    	done: false, // Always initiate as false
    	deadline: '2022-06-26'
    }
    ```

- **GET -** `/listTODO/{userid}`

    This route must receive the `id` of a user by `pathParameters` (the same id that was used to create some *todo*).

    The route must return *all* that have the `user_id` equal to the `id` received by the parameters.

<br />

## 💻 Downloading, installing dependencies and running the Project
**1.** Clone this repository
```
git clone git@github.com/felpst/serverless-challenge

``` 
**2.** Go to the project root directory
```
cd ignite-challenge-serverless
``` 
**3.** Install the necessary dependencies
```
yarn install
```
**4.** Create the .env file (using .env.example as an example)
```
cp .env.example .env
```
**5.** Install and start dynamoDB
```
serverless dynamodb install
serverless dynamodb start
```
**6.** Run the application
```
yarn dev
```

<br />

## Using the Application
To perform **requests** in the application, **Insomnia** or **Postman** must be used, importing the requests [file](insomnia).
