# TP8: Microservices with Dynamic API Gateway (Kong)

This project demonstrates the use of Kong as a dynamic API Gateway to manage multiple microservices (Users and Products) in a Dockerized environment. The services are built with Node.js and use Docker Compose to orchestrate the microservices and Kong.

## Project Structure

tp-kong/ ├── service-a/ │ ├── Dockerfile │ ├── package.json │ ├── index.js ├── service-b/ │ ├── Dockerfile │ ├── package.json │ ├── index.js ├── kong.yml ├── docker-compose.yml


## Requirements

- Docker and Docker Compose installed on your machine.
- Node.js (v22) and npm.
- Curl or Postman for testing the endpoints.

## Setup and Installation

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/tp8.git
   cd tp8


   
Build and start the services using Docker Compose:
docker-compose up --build

This will start the following services:

Service A (Users): A simple Node.js service running on port 3001.

Service B (Products): A simple Node.js service running on port 3002.

Kong API Gateway: Running on port 8000 (proxy) and port 8001 (admin API).

Verify that the services are running:
docker-compose ps


Testing the Microservices
Once the services are up and running, you can test them via curl or Postman.

1. Test the /users endpoint:
bash
Copier le code
curl http://localhost:8000/users
2. Test the /products endpoint:
bash
Copier le code
curl http://localhost:8000/products
If everything is set up correctly, you should receive JSON responses from both services.

Admin API (Kong)
You can manage Kong's configuration using its Admin API at port 8001.

List all services in Kong:
bash
Copier le code
curl http://localhost:8001/services
Access Kong's Admin API to manage services, routes, and more.


Files in this Project
service-a/Dockerfile: Defines how to build the service-a Docker container.

service-b/Dockerfile: Defines how to build the service-b Docker container.

kong.yml: Kong's declarative configuration file that defines routes and services.

docker-compose.yml: Defines the services and network configuration for Docker Compose.

