## Show all service principals that belongs to me.
```
az ad sp list --show-mine --output table | tee mysp.txt
az ad sp list --show-mine --output table | tee /mnt/c/amp/mysp.csv
```
## Kubernets-on-ubuntu-vmss 
[Azure Quickstart Template link](https://github.com/Azure/azure-quickstart-templates/tree/master/kubernetes-on-ubuntu-vmss/scripts)