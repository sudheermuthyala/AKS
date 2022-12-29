## Kubernetes - PODs
# PODs Introduction
- What is a POD ?
- What is a Multi-Container POD?
#  PODs Demo
Get Worker Nodes Status
- Verify if kubernetes worker nodes are ready.
```
# Configure Cluster Creds (kube config) for Azure AKS Clusters

az aks get-credentials --resource-group <Resource-Group-Name> --name <Cluster-Name>

# Replace Resource Group & Cluster Name

az aks get-credentials --resource-group aks-rg-1 --name aks-Demo-cluster

# Get Worker Node Status
kubectl get nodes

# Get Worker Node Status with wide option
kubectl get nodes -o wide
```

## Create a Pod
- create Pod

```
# Template
kubectl run <desired-pod-name> --image <Container-Image> 

# Replace Pod Name, Container Image
kubectl run ms-first-pod --image stacksimplify/kubenginx:1.0.0
```