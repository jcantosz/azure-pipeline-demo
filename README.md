# azure-pipeline-demo

## Purpose
App for demoing azure ecosystem, including: 
- Azure Devops
- ACR
- AKS

## Services set up
REF: https://docs.microsoft.com/en-us/azure/devops/pipelines/languages/aks-template?view=azure-devops
### Create a resource group
```
az group create --name myapp-rg --location eastus
```
### Create a container registry
```
az acr create --resource-group myapp-rg --name myContainerRegistry --sku Basic
```

### Create a Kubernetes cluster
```
az aks create \
    --resource-group myapp-rg \
    --name myapp \
    --node-count 1 \
    --enable-addons monitoring \
    --generate-ssh-keys
```


