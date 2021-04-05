# twtr-jwt

## Introduction

* This is an application similar to twitter where we can login and post tweets and see the tweets of other users
* The communication is made secure with JWT
* The application can be run locally with the help of docker-compose
* Utilized Amazon Elastic Container Registry (ECR) image registry to store built images
* Configured CodeBuild to run when code is checked in to GitHub which will automatically generate docker images with prod tags=
* Configured an Application Load Balancer (ALB) along with ECS to run a set of microservices
* Sent container logs to CloudWatch


### Prerequisites

* Node.js
* Python 3.7+
* AWS CLI
* Docker

### Setup

* Clone the repo from here -> https://github.com/sdileepkumarreddy/twtr-jwt.git

### How to Run??

* Navigate to react -> fe and execute `npm install` and then `npm start`. website can be accessed here  "http://localhost:3007"
* Navigate to python -> be and execute `python twtr.py`. website can be accessed here  "http://localhost:5000" (Set REACT_APP_API_SERVICE_URL=http://localhost:5000)
* It can also be run using docker compose. Inside the downloaded folder execute `docker-compose build` and `docker-compose up –d`. Applications can be accessed at `http://localhost:3007`
and `http://localhost:5004/tweets`
* AWS codebuild can be configured with buildspec.yml file present in Repo by connecting with the git hub repo url to codebuild
* Codebuild will build the code and generate docker images and push the images to ECR
* Continuous Delivery is achieved through ALB. Create an ALB and do necessary configuration and application can be accessed via ALB URL


