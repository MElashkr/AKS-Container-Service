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

**Available extensions for the Azure CLI**
<br/>Install extension by CLI. [CLI-Extension](https://docs.microsoft.com/en-us/cli/azure/azure-cli-extensions-list)
```
# get a list of extensions
az extension list-available --output table

# install the AKS extension
az extension add --name aks-preview
```

**Configure kubectl to connect to AKS**
<br/>Configure kubectl to connect to your Kubernetes cluster using the az aks get-credentials command
```
az aks get-credentials --resource-group myResourceGroup --name myAKSCluster
```

**Verify Connection to Cluster**
Verify the connection to your cluster using the kubectl get command.
```
kubectl get nodes
```
![alt text](https://github.com/MElashkr/AKS-Container-Service/blob/main/Pictures/kubectl.JPG)

**Azure CLI Sampels**
<br/>There are some sampels about Azure-CLI in GitHub
[Azure CLI Sampels](https://github.com/Azure-Samples/azure-cli-samples)

**AKS Command Sampels (from Kubernetes)**
<br/> [AKS CMD sampels](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#cluster-info)

**AZ-Commands (From MS)**
<br/> [AZ commands](https://docs.microsoft.com/en-us/cli/azure/reference-index?view=azure-cli-latest)

## Deployment and connect to AKS-Service by commands

**Apply deployment by yaml-file**
```
kubectl apply -f yourfile.yaml
```

**Display the number of pods**
```
kubectl get pod
```

**Display running services**
```
kubectl get service
```

**How to validate the service has the right pod**
<br/>you get the IP,Port, TargetPort(if you defiend it), Endpoints(is the IPs of the pods, which the servie must forward the request to) and more...
```
kubectl describe service your-service-name
```

**Display more infos about pod**
<br/> -o stands for output
```
kubectl get pod -o wide 
```

**Save status of deployment in a file**
<br/> Kubernetes generates status automatically. we need to get the result of updated information f.e of deployment whiche is stored in "etcd-db"
<br/> "> nginx-deployment-muster-result.yaml" means, you save status in a file(it can be helpful by debugging)
```
kubectl get deployment nginx-deployment-muster -o yaml > nginx-deployment-muster-result.yaml
```

**Delete configuration file**
```
kubectl delete -f yourfile.yaml
```




