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

## Create a Pod [Imperative]
- create Pod

```
# Template
kubectl run <desired-pod-name> --image <Container-Image> 

# Replace Pod Name, Container Image
kubectl run msNaidu-first-pod --image stacksimplify/kubenginx:1.0.0
```

## List Pods
- Get the list of pods
```
# List Pods
kubectl get pods

# Alias name for pods is po
kubectl get po
```
## List Pods with wide option
- List pods with wide option which also provide Node information on which Pod is running
```
kubectl get pods -o wide
```

## What happened in the backgroup when above command is run?
1. Kubernetes created a pod
3. Pulled the docker image from docker hub
4. Created the container in the pod
5. Started the container present in the pod

## Describe Pod
- Describe the POD, primarily required during troubleshooting.
- Events shown will be of a great help during troubleshooting.
```
# To get list of pod names
kubectl get pods

# Describe the Pod
kubectl describe pod <Pod-Name>
kubectl describe pod my-first-pod 
```
## Access Application
- Currently we can access this application only inside worker nodes.
- To access it externally, we need to create a NodePort or Load Balancer Service
- Services is one very very important concept in Kubernetes.

## Delete Pod
```
# To get list of pod names
kubectl get pods

# Delete Pod
kubectl delete pod <Pod-Name>
kubectl delete pod my-first-pod
```

## Load Balancer Service Introduction
- What are Services in k8s?
- What is a Load Balancer Service?
- How it works?

## Demo - Expose Pod with a Service (Load Balancer Service) 
- Expose pod with a service (Load Balancer Service) to access the application externally (from internet)
- **Ports**
    - **port**: Port on which node port service listens in Kubernetes cluster internally
    - **targetPort**: We define container port here on which our application is running.
- Verify the following before LB Service creation
    - Azure Standard Load Balancer created for Azure AKS Cluster
