How to use reference to a storage account?
Here is an example about how to use reference account.  
```
   "diagnosticsProfile": {
          "bootDiagnostics": {
            "enabled": true,
            "storageUri": "[reference(variables('newStorageAccountName')).primaryEndpoints.blob]"
          }
        }
      },

```