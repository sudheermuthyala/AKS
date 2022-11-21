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
    - So command line tools, like kube CTL, or users,and even the master components like scheduler,controller manager, and etcd,and worker node components like kubelet.Everything can talk to this kube APA server to perform the operations on the master,and selects a node for them to run on.across multiple nodes,

* **AKS kube Controller Manager :**
    - So controllers are responsible for noticing,and then responding when nodes, containers,or endpoints go down.
    - So we'll have different controllers available here.
    - So `node controllers` who are responsible for noticing
and responding when worker nodes are down.

Our replication controllers, responsible for maintaining

the correct number of ports for every application.

Our endpoint controllers, and then service account,

and then token controllers.

So, many controllers will be available for us

under this kube controller manager.

And let's go to the worker nodes.

So in worker nodes, again, the common thing here

is container runtime, right?
# In Regular Kubernets 
* Worker Nodes

# In EKS (aws)
* Managed Node Groups 