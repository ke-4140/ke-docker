# KE Docker
This is the docker deploy repository for the project KE. With docker, it should be able to deploy on any linux machine.

## Server Configuration
1. Start a instance on AWS
2. Associate a domain with the public IP address of the instance
3. Configure Security Group Policy to allow access of the following port: 
   * Public access (Source: 0.0.0.0/0)
     * Web: 80
   * Protected access, allowed in CUHK network only (Source: 137.189.0.0/16)
     * SSH: 22
     * MySQL: 3306

## Deployment Flow
1. Setup docker following the guide on the official docker website.
2. Setup docker-compose
3. Clone all repositories (ke-docker, ke-backend, ke-frontend) under home directory
4. cd into this repository and run '''docker-compose up --build'''
5. finish setup on other repositories
