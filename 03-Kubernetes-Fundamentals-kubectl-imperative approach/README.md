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
* **etcd :**
    - ETCD Is Nothing But Consistently highly avillable key value store
    - Used as a kubernetes backing store for all cluster Data it stores all Master and Node information.