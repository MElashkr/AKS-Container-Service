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
Go to Sunscription -> Resource providers -> type container und get this 3 services
* Microsoft.ContainerInstance
* Microsoft.ContainerRegistry
* Microsoft.ContainerService

References:
https://stackify.com/azure-container-service-kubernetes/
