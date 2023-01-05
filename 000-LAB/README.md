## 1. Create pod 

```
kubectl run pod <Desired-podname> --image stacksimplify/kubenginx:1.0.0 

```
## 2. Expose Pod with a Service (Load Balancer Service)

```
kubectl expose pod <>
```