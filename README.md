This React application has a dependency on another node project(node-api-server), which serves as a middleware.
It provides REST API's for consuming movie related information. This react application assumes the node-api-server is running on port 5000. This node middleware could have been anything like Spring-Boot-Application or any other micro-service. It could even be a AWS Lambda call (serverless). For brevity, the node application uses data in memory, rather than making further database call. Although it gives a complete end-to-end view of the architecture.

## Pre-requisite

To Run this React application, ensure you follow the instruction provided in ReadMe file of node-api-server project, which can be found [here](https://github.com/mukesh51/c1-node-api-server). The only constraint for this react application (as of now), is node-api-server should run on port 5000.

To run this application, ensure you clone this repository, move to that directoy and run `npm install` command.

Next run the following command `npm start` to start your react application.

The flow of the application goes as follows:

1. React Application starts up and tries to render the default component (in this case Movies component).
2. Movies Component in it's lifecycle method makes an asynchronous call (using axios) to REST endpoint provided by node-api-server application.
3. The above call returns a promise, which eventually gets resolved, as long as the node-api-server is up and running on port 5000. This port should ideally be set as an environment variable. Something to work on.
4. Once the prmoise is fullfilled, react application updates it's state and which triggers a re-render of the component.
5. Node-APi-Server application provides all the REST interfaces for CRUD operation. The react application for now, only show-cases Get and Delete endpoints. Other end-points can be accessed via POST-Man client for now.

#### Home page of React App. 
The movies are rendered by making a rest call to node-api-server application

![Home Page](https://github.com/mukesh51/c1-moviesbuster/blob/master/images/home-page.png)

### Screenshot of Accessing REST Endpoint can be found [here](https://github.com/mukesh51/c1-node-api-server/blob/master/README.md)
