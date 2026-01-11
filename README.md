# Welcome to operator-config repository
This repository contains configuration files that are used in ArgoCD. There are two separate folders, each representing the environment of the application:
* `catalog-service-dev` - contains configurations for the application in development environment
* `catalog-service-prod` - contains configurations for the application in production environment
Furthermore, each folder contains two configuration files:
* `deployment.yaml` - contains deployment information of the application. This includes the image used to deploy, the port opened, and the number of replicas. Jenkins would update the image tag after each build, if a new tag is available.
* `service.yaml` - contains servicing information of the application. This also includes information about the subnet and its elastic IP allocated for the application. While the elastic IP can be accessed during the demonstration of the project, to save costs, these are not available after the demonstration.

## Pre-requisites and setting up
To use the configurations, ArgoCD is required to be installed in an Amazon Elastic Kubernetes Service cluster group, which also has to have access to the images themselves. (via Amazon Elastic Container Registry) These configurations can then be linked to the application itself via setting them up in the manifest files during the creation of the application in ArgoCD.