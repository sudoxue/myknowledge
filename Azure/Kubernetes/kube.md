## How to get the token for kubernetes Dashboard?
You need to get secret from kube-system namespace
```
kubectl get secret -n kube-system
```
find the key and describe it.
```
kubectl describe secret kubernetes-dashboard-token-bz8v9
```
 ![test](Azure/Kubernetes/images/kdash-boardkey.png)