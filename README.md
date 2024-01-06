# Introduction

Build security with your services using Spring Cloud Security with OAUth2 Authentication service using OAuth2.  

It uses Spring Cloud Security to build a standard Spring Cloud OAuth2 service.  The OAuth2 service will create an OAuth2 token for a user.  Every protected service will need to take that service and callback into the OAuth2 service to validated.

Below are the functionlities that this project provides:

1. A Spring Cloud based OAuth2 authentication service that can issue and validate OAuth2 tokens.  

2. A Spring Cloud Config server that is deployed as Docker container and can manage a services configuration information using a file system or GitHub-based repository.

3. A Eureka server running as a Spring-Cloud based service.  This service will allow multiple service instances to register with it.  Clients that need to call a service will use 
    Eureka to lookup the physical location of the target service.

4.  A Zuul API Gateway.  All of our microservices can be routed through the gateway and have pre, response and post policies enforced on the calls.

5.  A organization service that will manage organization data used within EagleEye.

6.  A new version of the organization service.  This service is used to demonstrate how to use the Zuul API gateway to route to different versions of a service.

7.  A special routes services that the the API gateway will call to determine whether or not it should route a user's service call to a different service then the one they were 
    originally calling.  This service is used in conjunction with the orgservice-new service to determine whether a call to the organization service gets routed to an old version of the organization service vs. a new version of the service.

8.  A licensing service that will manage licensing data used within EagleEye.

9.  A Postgres SQL database used to hold the data for these two services.


## Software needed
1. [Apache Maven] (http://maven.apache.org)
2. [Docker] (http://docker.com)
3. [Git Client] (http://git-scm.com)

## Building Docker Images 


   **mvn clean package docker:build**


## Running service


   **docker-compose -f docker/common/docker-compose.yml up**

