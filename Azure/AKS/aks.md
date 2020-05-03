## Show all service principals that belongs to me.
```
az ad sp list --show-mine --output table | tee mysp.txt
az ad sp list --show-mine --output table | tee /mnt/c/amp/mysp.csv
```
