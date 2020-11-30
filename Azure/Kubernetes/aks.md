## Show all service principals that belongs to me.
```
az ad sp list --show-mine --output table | tee mysp.txt
az ad sp list --show-mine --output table | tee /mnt/c/amp/mysp.csv
```
## Kubernets-on-ubuntu-vmss 
[Azure Quickstart Template link](https://github.com/Azure/azure-quickstart-templates/tree/master/kubernetes-on-ubuntu-vmss/scripts)

## How to connect to kubernetes cluster? 
```
az aks get-credentials --resource-group mxue --name aks101cluster
Merged "aks101cluster" as current context in /home/michael/.kube/config
michael@Azure:~$ kubectl get nodes
```
NAME                       STATUS   ROLES   AGE   VERSION
aks-agentpool-37134733-0   Ready    agent   57m   v1.15.10
aks-agentpool-37134733-1   Ready    agent   57m   v1.15.10
aks-agentpool-37134733-2   Ready    agent   57m   v1.15.10
michael@Azure:~$ kubectl run nginx --image nginx
kubectl run --generator=deployment/apps.v1 is DEPRECATED and will be removed in a future version. Use kubectl run --generator=run-pod/v1 or kubectl create instead.
deployment.apps/nginx created
michael@Azure:~$ kubectl get pod
NAME                     READY   STATUS    RESTARTS   AGE
nginx-7bb7cd8db5-pkxl6   1/1     Running   0          16s
michael@Azure:~$

### How to add line number to VIM

Press the Esc key if you are currently in insert or append mode
Press :(the colon). The cursor should reappear at the lower left corner of the screen next to a:
Enter the following command: 
```
set number
```