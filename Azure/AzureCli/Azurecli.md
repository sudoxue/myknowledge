## How to swith to the subscription?
```
az account list
az account set -s fbc19e08-7593-43a2-ae1e-798aad464d69
```
## How to create a resource group
```
az deployment group create -g mxue -l eastus
```
## How to deploy resource in a group
```
az deployment group create -g mxue -f azuredeploy.json
```
## how to list vm size in a location
```
az vm list-sizes -l westus
```