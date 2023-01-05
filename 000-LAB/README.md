## 1. Create pod 

```
kubectl run pod <Desired-podname> --image stacksimplify/kubenginx:1.0.0 


```
## 2. Expose Pod with a Service (Load Balancer Service)

```
kubectl expose pod <pod-name> --type=LoadBalancer --port=80 --name=<Desired-Service-name>
kubectl expose pod 
```