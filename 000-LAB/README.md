## 1. Create pod 

```t
# syntax
kubectl run pod <Desired-podname> --image stacksimplify/kubenginx:1.0.0 

# example
kubectl run msn-first-pod --image stacksimplify/kubenginx:1.0.0 


```
## 2. Expose Pod with a Service (Load Balancer Service)

```t
# Syntax
kubectl expose pod <pod-name> --type=LoadBalancer --port=80 --name=<Desired-Service-name>

# example 
kubectl expose pod msn-first-pod --type=LoadBalancer --port=80 --name=myfirst-services-loadbalancer

# To check the service 

```