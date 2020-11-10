# Challenge3-Will
This will be the same as challenge 2, except I will do everything via Azure DevOps instead of Jenkins.  The AKS will be used as well.  This sample application is the one used: https://github.com/hibby96/sample-web-app

You will see the Azure Pipeline file on the root of the main branch in that repository.

## Creation of AKS
The AKS was created with the Azure CLI tool.  The following commands were run:

```
az group create -l eastus -n rgaks
az aks create -g rgaks -n myAKS --node-count 2 -s Standard_B2s
az aks get-credentials -g rgaks -n myAKS
az acr create --name willHacr --resource-group rgAKS --sku Basic --admin-enabled true --location eastus
```

As you can see, I also opted to use an Azure container repository rather than Dockerhub.  
