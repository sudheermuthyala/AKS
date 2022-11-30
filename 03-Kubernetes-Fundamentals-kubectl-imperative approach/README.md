## Kubernetes-Fundamentals-kubectl-imperative approach
# Understand Kubernetes Architecture
- So Kubernetes is a portable, extensible,open source platform for managing container workloads.
    - out of the box the following features are available in Kubernetes.
        - Service discovery and load balancing,
        - storage orchestration, 
        - automated rollouts and rollbacks,
        - automatic bin packing, 
        - self-healing,
        - secrets and configuration management.

##  Kubernetes components in its architecture
- So primarily, we see like we'll have both master and then worker nodes in the Kubernetes.
- And on all these nodes we'll have the container runtime installed.Whether it is master or worker nodes,
container runtime is mandatory

*  **Container Runtime (Docker):** 
    - This is common across the Master and the worker Nodes. to runn our respective pods component present in side that master  
* **etcd :**
    - ETCD Is Nothing But Consistently highly avillable key value store
    - Used as a kubernetes backing store for all cluster Data it stores all Master and Node information.
* **Kube-Sheduler :**
    - So it is responsible for distributing containers across multiple nodes,which is nothing but multiple worker nodes.
    - It watches for newly created pods with no assigned node and selects a node for them to run on.
* **Kube-APIServer :**
    - So it acts as a front end for the Kubernetes control plane. It exposes the Kubernetes API.
    - So command line tools, like `kubectl`, `users`,and even ***master components*** like `scheduler`,`controller manager`, and `etcd`,and ***worker node components*** like `kubelet`.Everything can talk to this kube-API-server to perform the operations on the master,and selects a node for them to run on.across multiple nodes,
    - It will Talk ot All the components in the ***master Node components*** and ***worker node components***

* **kube Controller Manager :**
    - kube Controller Manager are responsible for noticing, then responding when nodes, containers,or endpoints go down.
    - So we'll have different controllers available here.
    - `node controllers` who are responsible for noticing and responding when worker nodes are down.
    - `replication controllers`, responsible for maintaining the correct number of ports for every application.
    - `endpoint controllers`, and then `service account`,and then `token controllers` So, many controllers will be available under this API kube controller manager.

* **Cloud Control Manager**
    

## Worker Node Components
* **container runtime :**  
    - So in worker nodes, again, the common thing here is container runtime and in container runtime is the underlying software where we run all the Kubernetes components.So we are using docker, but we have other runtime optionslike RKTR, container D, etc.

* **Kubectl :** 
    - kubelet it is hart for the worker nodes. kubelet is the agent that runs on every node in the cluster agent is responsible for making sure that containers are running in a pod on a node.And these will be always in constant communication with the `kube-scheduler` So kube-scheduler, from master node, talks to worker nodes to the kubelet.

* **Kube-Proxy :**
    -  So it is a network proxy that runs on each node in your cluster It maintains the network rules on the nodes
<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/2022-11-30-14-39-01.png" />
    </p>

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/01-Create-AKS-Cluster/2022-11-21-16-03-54.png" />