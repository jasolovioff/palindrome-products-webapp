# Palindrome product search prototype

This prototype implements a functionality that applies a 50% discounts on all the products found trough a search done with a palindrome.

## Solution composition

The solution is composed by the following elements:
* Web server built with NodeJS and Express
* A web application built in React with the help of Redux
* A MongoDB to store the products

## Run locally for development
The solution can be  mounted locally for development using a NodeJS for the webapp and Docker for the database.

### Mounting database
An instance of the database with test products can be find in the following GitHub repository:
https://github.com/walmartdigital/products-db

Clone it locally, and follow the instructions to run the container and load the data.

### Running the web application
To run the application locally, first the npm packages must be installed.
On the root directory of the project run this command:
```shell script
$ npm install
```
To start the application in dev mode, run the following command:
```shell script
$ npm run dev
```

## Deploy on Heroku
This solution is already deployed on Heroku and can be visited on the following URL:
https://palindrome-products.herokuapp.com/

From this location, the web app is served, the database is stored in MongoDB Atlas (https://www.mongodb.com/cloud/atlas).

### Deploy in another Heroku instance
To deploy this solution in another Heroku instance this steps must be followed:
* Clone the repository
* Create a MongoDB atlas cluster with a database called `promotions` and a collection called `products`.
* Import the products database that can be found in https://palindrome-products.herokuapp.com/ , to the MongoDB Atlas cluster using mongoimport.
  * Notice that you have to create database user credentials and grant proper network permissions.
* Deploy the application to Heroku using any of the followin options (details can be found at https://devcenter.heroku.com/categories/deploying-with-docker):
  * Deploy directly from Heroku CLI
  * Deploy via GitHub linking a repository with the target instance
* Remember to set the following environmental variables:
  * NODE_ENV : always set to `production`
  * MONGO_URI : the URL of the MongoDB Atlas database
  * MONGO_USER : the MongoDB user
  * MONGO_PASS : the MongoDB user password


