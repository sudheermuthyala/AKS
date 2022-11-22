## Introduction
- Understand about AKS Cluster
- Discuss about Kubernetes Architecture from AKS Cluster perspective

##  Create AKS Cluster
- Create Kubernetes Cluster
- **Basics**
  - **Subscription:** Free Trial
  - **Resource Group:** Creat New: aks-rg1
  - **Kubernetes Cluster Name:** aksdemo1
  - **Region:** (US) Central US
  - **Kubernetes Version:** Select what ever is latest stable version
  - **Node Size:** Standard DS2 v2 (Default one)
  - **Node Count:** 1
- **Node Pools**
  - leave to defaults
- **Authentication**
  - Authentication method: 	System-assigned managed identity
  - Rest all leave to defaults
- **Networking**
  - **Network Configuration:** Advanced
  - **Network Policy:** Azure
  - Rest all leave to defaults
- **Integrations**
  - Azure Container Registry: None
  - leave to defaults
- **Tags**
  - leave to defaults
- **Review + Create**
  - Click on **Create**

##  Cloud Shell - Configure kubectl to connect to AKS Cluster
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

##  Explore Cluster Control Plane and Workload inside that
```
# List Namespaces
kubectl get namespaces
kubectl get ns

# List Pods from all namespaces
kubectl get pods --all-namespaces

# List all k8s objects from Cluster Control plane
kubectl get all --all-namespaces
```
 # Explore the AKS cluster on Azure Management Console
- Explore the following features on high-level
- **Overview**
  - Activity Log
  - Access Control (IAM)
  - Security
  - Diagnose and solver problems
- **Settings**
  - Node Pools
  - Upgrade
  - Scale
  - Networking
  - DevSpaces
  - Deployment Center
  - Policies
- **Monitoring**
  - Insights
  - Alerts
  - Metrics
  - and many more 
- **VM Scale Sets**
  - Verify Azure VM Instances
  - Verify if **Enhanced Networking is enabled or not**  

## Local Desktop - Install Azure CLI and Azure AKS CLI
```
# Install Azure CLI (Windo)
winget install -e --id Microsoft.AzureCLI

# Install Azure AKS CLI
az aks install-cli

# Login to Azure
az login

# Configure Cluster Creds (kube config)

az aks get-credentials --resource-group aks-rg-1 --name aks-Demo-cluster

# List AKS Nodes
kubectl get nodes 
kubectl get nodes -o wide
```
- **Reference Documentation Links**
- https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest
- https://docs.microsoft.com/en-us/cli/azure/aks?view=azure-cli-latest


## Deploy Sample Application and Test

```
# Deploy Application
kubectl apply -f kube-manifests/

# Verify Pods
kubectl get pods

# Verify Deployment
kubectl get deployment

# Verify Service (Make a note of external ip)
kubectl get service

# Access Application
http://<External-IP-from-get-service-output>
```