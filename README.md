# AKS-Container-Service
Goal for this tutorial is Creating AKS container service on Azure and deploy Web-App on it

## Introduction

Installing, configuring, and maintaining a Kubernetes cluster could distract your company from the things that provide value. 
Azure provides AKS as PaaS. On the other hand, does not charge you for Kubernetes masters—you only pay for the nodes (minions) where your containers will be deployed.
There’s also a cooler service called Azure Container Instances (ACI), which is the “serverless” offering for Docker containers in Azure. What’s nice about this service is that you can scale Kubernetes using ACI

## Prerequisites
Before you start, you need to have the following:

1. An Azure account with a subscription. You need a credit card, but don’t worry—you’ll get initial free credits when you start a subscription. You can also get some free credits if you have an MSDN subscription or if you sign up for the Dev Essentials program. If you know more ways to get free credits, let me know in the comments section.
2. Azure CLI installed and configured.
3. Kubernetes command-line tool kubectl installed.
4. Lastly, make sure the Azure subscription you use has these required resources: Storage, Compute, Networking, and ContainerService. If you’re not sure how to register resources in the subscription, read on!

## Register required resources in the subscription
you need to register some resources in your subscription:
Go to your Subscription -> Resource providers -> type container und get this 3 services
* Microsoft.ContainerInstance
* Microsoft.ContainerRegistry
* Microsoft.ContainerService

![alt text](https://github.com/MElashkr/AKS-Container-Service/blob/main/Pictures/Register-AKS-Service.JPG?row=true "Register necessary resources for AKS-Service")

Note: if Storage, Compute, Networking, and ContainerService are not registered, then click on the “Register” (2) link and wait a little bit.

## Steps to Create AKS-Service

### Step 1: Creating an AKS/Azure Container Service cluster using the Azure Portal
* **Create Kubernates Service**
<br/>Currently, an Azure Kubernetes Service (AKS) cluster (specifically, the Kubernetes cloud provider) requires an identity to create additional resources like load balancers and managed disks in Azure. This identity can be either a managed identity or a service principal. If you use a service principal, you must either provide one or AKS creates one on your behalf. If you use managed identity, this will be created for you by AKS automatically. [AKS Authentication](https://docs.microsoft.com/de-de/azure/aks/use-managed-identity)
![alt text](https://github.com/MElashkr/AKS-Container-Service/blob/main/Pictures/Create-AKS-Cluster.JPG?row=true "Create AKS-Cluster")

* **Configurate Auhtenticaiton section**
<br/>There are two options by configuration of the authentication
1. Service Principal
2. System-assigned management identity
![alt text](https://github.com/MElashkr/AKS-Container-Service/blob/main/Pictures/Create-AKS-Cluster-Authentication.JPG?row=true "Configurate AKS-Cluster-Authentication")

* **Configurate Integration Section**
<br/>It is possible to connect your AKS-Cluster with an Azure Container Registery during creation of AKS-Cluster
![alt text](https://github.com/MElashkr/AKS-Container-Service/blob/main/Pictures/Create-AKS-Cluster-Integration.JPG?row=true "Configurate AKS-Cluster-Integration")


References:
* https://stackify.com/azure-container-service-kubernetes/
* https://docs.microsoft.com/de-de/azure/aks/use-managed-identity
