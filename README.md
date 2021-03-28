# spacex-api-test

Simple Postman/Newman tests for the endpoint **GET https://api.spacexdata.com/v4/launches/latest**, covering what I consider
the three most critical scenarios.

##Critical Scenarios 

### Endpoint returns 200
The request has succeeded. The GET endpoint has been fetched and is transmitted in the message body.

### Response time is less than 1000ms
If the response takes longer than a second, then it indicates an issue that needs to be investigated. The 1 second time is based
on the fact that the average time has not gone above it after several executions, setting it as a baseline. 

### Schema Validation
Schemas are a special, object-based way of defining validations or sanitizations on requests. It is critical to check if the body
message respects the specified validation object.

###  Project Dependencies

* npm - required to install Newman
* Newman - command line way to execute 
* [Postman](https://www.postman.com/downloads/) - edit, visualize and execute by using the graphical interface

### Installation

* Install npm https://www.npmjs.com/get-npm
* Install Newman
  
        $ npm install -g newman

### Running the collection

        $  newman run collection/SpaceXAPITesting.postman_collection.json -e environment/TestEnvironment.postman_environment.json

