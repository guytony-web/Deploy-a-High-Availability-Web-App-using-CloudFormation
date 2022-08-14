# Deploy a high-availability web app using CloudFormation

In this project, we deployed web servers for a highly available web app using CloudFormation.

## Project Overview

Your company is creating an Instagram clone called Udagram. Developers want to deploy a new application to the AWS infrastructure. 
You have been tasked with provisioning the required infrastructure and deploying a dummy application, along with the necessary supporting software.

## Diagram of the Infrastructure

![Architecture](Architecture.jpeg)

## Project Files
- `create.sh`: This contains script to create CloudFormation stack.
- `delete.sh`: This contains script to delete CloudFormation stack
- `update.sh`: This contains script to update CloudFormation stack
- `Architecture.jpeg`: This describes the architecture diagram of this project.
- `Network_parameters.json`: Parameters file for network cloud formation stack.
- `Network.yml`: CloudFormation template for creating networking resources for this project.
- `Servers-paramaters.json`: Parameters file for servers cloud formation stack.
- `Servers.yml`: CloudFormation template for creating servers for this project.

## Prerequisite
- AWS Account
- Visual Studio
- AWS CLI
- python

## Project Setup

- Create networking resources 
```
$ create.sh webapp-network-stack network.yml Network_parameters.json
```
-   Following resources are created:
    -   VPC
    -   Subnets
    -   Route Tables
    -   Routes
    -   Internet Gateway
    -   NAT Gateways
- Create servers for ours infrastructure .
```
$ create.sh webapp-servers-stack servers.yml servers-paramaters.json
```
-   Following resources are created:
    -   Security Groups
    -   Instances
    -   Launch configuration
    -   Auto Scaling Group
    -   Load Balancer
    -   Target Group
- The URL of application can be find from the outputs section of `webapp-servers-stack` CloudFormarion stack.
