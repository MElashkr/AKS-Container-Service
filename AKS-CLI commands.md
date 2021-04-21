# Connect to Cluster

**Install AKS-CLI**
<br/>To manage a Kubernetes cluster, use the Kubernetes command-line client, kubectl. kubectl is already installed if you use Azure Cloud Shell.
[AKS-CLI](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough)
```
az aks install-cli
```

**Show Cluster Info**

```
az aks show --name
            --resource-group
            [--query-examples]
            [--subscription]
```
**Exampel**
<br/>Show the details for a managed Kubernetes cluster
```
az aks show --name MyManagedCluster --resource-group MyResourceGroup
```
