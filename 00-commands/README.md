## List of Kubernetes Commands
# List Kubernetes Worker Nodes
```
kubectl get nodes 
kubectl get nodes -o wide
```

## Explore Cluster Control Plane and Workload inside that
# List Namespaces

```
# List Namespaces
kubectl get namespaces
kubectl get ns

# List Pods from all namespaces
kubectl get pods --all-namespaces

# List all k8s objects from Cluster Control plane
kubectl get all --all-namespaces
```

# Deploy Application
```
kubectl apply -f kube-manifests/

# Verify Pods
kubectl get pods

# Verify Deployment
kubectl get deployment
kubectl get deploy (alias)


# Verify Service (Make a note of external ip)
kubectl get service
kubectl get svc (alias)

# Access Application
http://<External-IP-from-get-service-output>
```

## To What are events Occured 
- kubectl describe pods `myapp1-deployment-6f6b58f6d7-9nz67`

## Configure Cluster Creds (kube config) for ***Azure AKS Clusters***

```t
# Configure Cluster Creds (kube config) for Azure AKS Clusters

az aks get-credentials --resource-group <Resource-Group-Name> --name <Cluster-Name>

# Replace Resource Group & Cluster Name

az aks get-credentials --resource-group aks-rg-1 --name aks-Demo-cluster

# Get Worker Node Status
kubectl get nodes

# Get Worker Node Status with wide option
kubectl get nodes -o wide

```