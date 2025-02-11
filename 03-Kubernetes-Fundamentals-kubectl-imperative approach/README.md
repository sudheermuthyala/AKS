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

## 1.Master Node COmponents
1. **Container Runtime (Docker):**
2. **etcd :**
3. **Kube-Sheduler :**
4. **Kube-API Server :API (application programming interface)**
5. **kube Controller Manager :**
6. **Cloud Control Manager**

*  **Container Runtime (Docker):** 
    - This is common across the Master and the worker Nodes. to runn our respective pods component present in side that master  
* **etcd :**
    - ETCD Is Nothing But Consistently highly avillable key value store
    - Used as a kubernetes backing store for all cluster Data it stores all Master and Node information.
* **Kube-Sheduler :**
    - A scheduler watches for newly created Pods that have no Node assigned.
    - For every Pod that the scheduler discovers, the scheduler becomes responsible for finding the best Node for that Pod to run on. 
    - Kube-scheduler selects an optimal node to run newly created or not yet scheduled (unscheduled) pods.
    - So it is responsible for distributing containers across multiple nodes,which is nothing but multiple worker nodes.
    
* **Kube-API Server :API (application programming interface)** 
    - Kube-API Server acts as a front end for the Kubernetes control plane. It exposes the Kubernetes API.
    - So command line tools, like `kubectl`, and `users`, even ***master components*** like `Kube-Sheduler`,`controller manager`, and `etcd`,and ***worker node components*** like `kubelet`.Everything can talk to this kube-API-server to perform the operations on the master,and selects a node for them to run on.across multiple nodes,
    - It will Talk ot All the components in the ***master Node components*** and ***worker node components***

* **kube Controller Manager :**
    - kube Controller Manager are responsible for noticing, then responding when **nodes**, **containers**,or **endpoints** go down.
    - So we'll have different controllers available here.
    - `node controllers` who are responsible for noticing and responding when worker nodes are down.
    - `replication controllers`, responsible for maintaining the correct number of ports for every application.
    - `endpoint controllers`, and then `service account`,and then `token controllers` So, many controllers will be available under this API kube controller manager.

* **Cloud Control Manager**
    

## 2.Worker Node Components

1. **container runtime :**
2. **Kubectl :**
3. **Kube-Proxy :**

* **container runtime :**  
    - So in worker nodes, again, the common thing here is container runtime and in container runtime is the underlying software where we run all the Kubernetes components.So we are using docker, but we have other runtime optionslike RKTR, container D, etc.

* **Kubectl :** 
    - kubelet it is hart for the worker nodes. kubelet is an agent that runs on every node in the cluster.
    - kubectl-agent is responsible for making sure that containers are running in a pod on a node.
    - And these will be always in constant communication with the `kube-scheduler` So kube-scheduler, from master node, talks to worker nodes to the kubelet.

* **Kube-Proxy :**
    -  So it is a network proxy that runs on each node in your cluster It maintains the network rules on the nodes
## Kubernets architecture

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-11-30-14-39-01.png" />
    </p>

# 19 Introduction to Kubernets Fundamentals
## k8s Fundamentals

 **Pod**
- A POD is a single instance of an Application. 
- A POD is the smallest object, that you can create in Kubernetes.

**ReplicaSet**
- A ReplicaSet will maintain a stable set of replica Pods running at any given time. 
- In short, it is often used to guarantee the availability of a specified number of identical Pods

**Deployment**
- A Deployment runs multiple replicas of your application and automatically replaces any instances that fail or become unresponsive.
- Rollout & rollback changes to applications. Deployments are well-suited for stateless applications.

**Service**
- A service is an abstraction for pods, providing a stable, so called virtual IP (VIP) address.
- In simple terms, service sits Infront of a POD and acts as a load balancer. 

Kubernetes - Fundamentals

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-12-29-12-01-47.png" />
    </p>

Kubernetes - Imperative & Declarative

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-12-29-12-21-20.png" />
    </p>



# 20.Introduction to Kubernetes Pods

## Kubernetes - POD
- With Kubernetes our core goal will be to deploy our applications in the form of containers on worker nodes in a k8s cluster.
- Kubernetes does not deploy containers directly on the worker nodes.
- Container is encapsulated in to a Kubernetes Object named POD.
- A POD is a single instance of an application.
- A POD is the smallest object that we can create in Kubernetes. 

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-12-29-12-33-40.png" />
    </p>

- PODs generally have one to one relationship with containers
- To scale up we create new POD and to scale down we delete the POD.

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-12-29-12-41-28.png" />
    </p>

- We `cannot` have multiple containers of same kind in a single POD. 
- Example: Two NGINX containers in single POD serving same purpose is **not recommended**.

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-12-29-12-43-34.png" />
    </p>

# Kubernetes – Multi-Container Pods
- We can have multiple containers in a single POD, provided they are not of same kind. 
- Helper Containers (Side-car)
    - Data Pullers: Pull data required by Main Container
    - Data pushers: Push data by collecting from main container (logs)
    - Proxies: Writes static data to html files using Helper container and Reads using Main Container. 
- Communication
    - The two containers can easily communicate with each other easily as they share same network space.
    - They can also easily share same storage space. 
- Multi-Container Pods is a rare use-case and we will try to focus on core fundamentals. 

<p align="center">
  <img src="https://github.com/sudheermuthyala/AKSDOCS/blob/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/images/2022-12-29-12-52-40.png" />
    </p>


## 21. [Create a Pod, Understand about it and delete pod](https://github.com/sudheermuthyala/AKSDOCS/tree/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/03-01-PODs-with-kubectl#kubernetes---pods)

## 22. [Load Balancer Service Introduction](https://github.com/sudheermuthyala/AKSDOCS/tree/main/03-Kubernetes-Fundamentals-kubectl-imperative%20approach/03-01-PODs-with-kubectl#load-balancer-service-introduction)
