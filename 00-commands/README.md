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

# Verify Service (Make a note of external ip)
kubectl get service

# Access Application
http://<External-IP-from-get-service-output>
```

- kubectl describe pod