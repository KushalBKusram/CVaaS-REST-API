# CVaaS-REST-API

## Technical Description
 A RESTful implementation of DBaaS using Docker, Python, Flask, MongoDB and TensorFlow.

## Concept
A database initialized using MongoDB with the objective to store username, encrypted password and provide image recognition services. Each user is allocated 6 tokens. The expense of each registration and image classification being 1 token. 

# Documentation

## Building:
1. Clone the repository. Make sure you have Docker installed on your machine. 
2. Run the following command within the root directory to initialize containers and build the application and the server: `docker-compose build`
3. Run the following command within the same root directory to deploy the application and start the server: `docker-compose up` or `docker-compose up -d` to run in detached mode. 
4. The server should be up and running at `localhost:5000` if everything successfully compiles, builds and containerizes. 

## Getting Started with API:

You may use a tool such as [Postman](https://www.postman.com/downloads/) to test the API with the following REST calls. 

- To register a user: `localhost:5000/register` </br>
    <strong>JSON:</strong>
    ```json
    {
        "username": "kushalbkusram",
        "password": "123xyz"
    }
    ```

- To classify an image: `localhost:5000/classify` </br>
    <strong>JSON:</strong>
    ```json
    {
        "username": "kushalbkusram",
        "password": "123xyz",
    }
    ```
    Note: The app has the functionality to parse an image from a URL and classify.

- To refill tokens: `localhost:5000/refill` </br>
    <strong>JSON:</strong>
    </br>
    ```json
    {
        "username": "kushalbkusram",
        "admin_pw": "abc123",
        "amount": 6
    }
    ```