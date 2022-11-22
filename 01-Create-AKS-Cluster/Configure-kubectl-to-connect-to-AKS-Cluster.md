## Configure kubectl to connect to AKS Cluster
# Cloud Shell
- Go to https://shell.azure.com 

```
# Template

az aks get-credentials --resource-group <Resource-Group-Name> --name <Cluster-Name>

# Replace Resource Group & Cluster Name

az aks get-credentials --resource-group aks-rg-1 --name aks-Demo-cluster

# List Kubernetes Worker Nodes
kubectl get nodes 
kubectl get nodes -o wide
```
