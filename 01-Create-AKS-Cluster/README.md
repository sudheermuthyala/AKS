# Create AKS Cluster
## Introduction
![](2022-11-21-14-41-59.png)
## Very high level AKS Kubernets architecture
![](2022-11-21-14-47-16.png)
## Key words 
# In Azure AKS
* Azure AKS Cluster Control Plaine (Master Node Component)
* Azure AKS Node Pools (Worker Node Component)
## Master Node COmponents
*  **Container Runtime (Docker):** 
    - This is common across the Master and the worker Nodes. to runn our respective pods component present in side that master  

* **etcd :**
    - ETCD Is Nothing But Consistently highly avillable key value store
    - Used as a kubernetes backing store for all cluster Data it stores all Master and Node information.

* **Kube-Sheduler :**
    - So it is responsible for distributing containers across multiple nodes,which is nothing but multiple worker nodes.
    - It watches for newly created parts with no assigned node and selects a node for them to run on.
* **Kube-APIServer :**
    - So it acts as a front end for the Kubernetes control plane. It exposes the Kubernetes APA.
    - So command line tools, like kube CTL, or users,and even the master components like scheduler,controller manager, and etcd,and worker node components like kubelet.Everything can talk to this kube APA server

to perform the operations on the master, right?

and selects a node for them to run on.

across multiple nodes,
# In Regular Kubernets 
* Worker Nodes

# In EKS (aws)
* Managed Node Groups 