<<<<<<< HEAD
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

## What is the difference between service principal and managed identity.
There are two ways to manage access through Azure Active Directory (Azure AD): service principals or managed identities for Azure resources.

Of the two ways, managed identities is recommended. With service principals, you are responsible for managing and rotating secrets, either manually or programmatically. With managed identities, Azure AD manages and performs the authentication and timely rotation of secrets for you.

As an example for the inside-out case, let’s study the use of managed identities when the cluster needs to pull images from a container registry. This action requires the cluster to get the credentials of the registry. One way is to store that information in the form of Kubernetes Secrets object and use imagePullSecrets to retrieve the secret. That approach isn't recommended because of security complexities. Not only do you need prior knowledge of the secret but also disclosure of that secret through the DevOps pipeline. Another reason is the operational overhead of managing the rotation of the secret. Instead, grant acrPull access to the managed identity of the cluster to your registry. This approach addresses those concerns.

## Can you give me an example of Azure build-in roles? 
```
Network Contributor
Monitorying Metrics Publisher
AcrPull

Azure AD integration also simplifies security for outside-in access. Suppose a user wants to use kubectl. As an initial step, sends the az aks get-credentials
```

## Let's talk about AKS supported networking model
AKS support two networking models: kubenet and Azure Container Networking Interfaces (CNI), CNI is more advanced of the two models and is required for enabling Azure Network Policy. In this model, every pod gets an IP address from the subnet address space. Resources within the same network (or peered resources) can access the pods directly through their IP address. NAT isn't needed for routing that traffic. So, CNI is performant because there aren’t additional network overlays. It also offers better security control because it enables the use Azure Network Policy. In general, CNI is recommended. CNI offers granular control by teams and the resources they control. Also, CNI allows for more scaled pods than kubenet. Carefully consider this choice otherwise, the cluster will need to be redeployed. For information about the models, see Compare network models.

=======
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
>>>>>>> 882b12c99dc6f2abe605b427339157e1767faa32
