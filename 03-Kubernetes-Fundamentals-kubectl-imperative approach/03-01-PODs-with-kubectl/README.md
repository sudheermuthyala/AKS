## Kubernetes - PODs
# PODs Introduction
- What is a POD ?
- What is a Multi-Container POD?
#  PODs Demo
Get Worker Nodes Status
- Verify if kubernetes worker nodes are ready.
```
# Configure Cluster Creds (kube config) for Azure AKS Clusters
az aks get-credentials --resource-group  --name aksdemo1

# Get Worker Node Status
kubectl get nodes

# Get Worker Node Status with wide option
kubectl get nodes -o wide
```