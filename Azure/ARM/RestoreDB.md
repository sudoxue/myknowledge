<!-- Headings -->
# ARM template FAQs
Answer: There are so many of them, there is no way you can remember all of that. 
        Microsoft.ContainerService resource types-managedClusters
### How "dependson" works
Resource Manager evaluates the dependencies between resources, and deploys them in their dependent order. When resources aren't dependent on each other, Resource Manager deploys them in parallel. You only need to define dependencies for resources that are deployed in the same template. 

### What is the difference between resource dependencies and Conditional deploy?
1. Conditionally deploy evaluate the statement is true or false dependencies does not. 
```
{
    "condition": "[equals(parameters('newOrExisting), 'new')]",
    "dependsOn": "[variables("loadbalancerName")]
}

```
2. How to set to subscription you want to deploy stuff.

<img src="https://aka.ms/deploytoazurebutton"/>
https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-storage-account-create/azuredeploy.json

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-1vm-2nics-2subnets-1vnet%2Fazuredeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.png"/>
</a>

3. Can I deploy subscription level resources?
 [Here is the link](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-to-subscription#create-roles)


<!-- Italics -->
This text* is italic
_This Text_is italic
<!-- Blockquote -->
>This is a quote

* Item1
* Item2
  * item3
1. nima
1. nima2

![Markdown Logo](https://markdown-here.com/img/icon256.png)


[Traversy Media](http://www.microsoft.com)
## 1. How many resources can ARM template deploy
## 2. Explain _artifactsLocation and _artifactsLocationSasToken
Answer: If you've created a deployment project, you've undoublely seen these two values in your template, if you've used linked templates, you have come to rely on these parameters.
These two values are used to create a URL which represents the complete path to the linked file, usually an ARM template or dependency that’s part of the same deployment. In order to use these values, they are exposed as parameters from the ARM template.The first value,_artifactsLocation, represents the base URL for a path where the documents will be staged. This path must be a publicly accessible URL. The _artifactsLocationSasToken is a query string appended to the URI, typically containing a generated SAS token. This ensures that a public reference exists for templates which are hosted in a private location. Concatenated in between these two values is the file being referenced: 
<!-- code blocks -->
...

[uri(parameters('_artifactsLocation'), concat('deploy.json', parameters('_artifactsLocationSasToken')))]

...

```
dsaf
```


| name | email|
|......|......|
|jongdou| zhu|

So, how do these values get populated? If you attempt to deploy the templates using Visual Studio, those values will show as auto-generated:For most other cases (or to have more control over the process), you will need to specify those values manually to ensure that any reference templates or files can be properly resolved.
_artifactsLocation - The base URI where all artifacts for the deployment will be staged. The defaultValue must be specified as shown and include a trailing slash when provided during deployment.
_artifactsLocationSasToken - The sasToken required to access _artifactsLocation. The default value should be an empty string "" for scenarios where the _artifactsLocation is not secured, such as the raw GitHub URI for a public repo. The following code shows an example:
  "parameters": {
      "_artifactsLocation": {
          "type": "string",
          "metadata": {
              "description": "The base URI where artifacts required by this template are located including a trailing '/'"
          },
          "defaultValue": "[deployment().properties.templateLink.uri]",  //use this for the Azure marketplace
          "defaultValue": "https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/[name of sample folder]/" // use this for a Quickstart in this repo (we're working on fixing this to match the marketplace...)
      },
      "_artifactsLocationSasToken": {
          "type": "securestring",
          "metadata": {
              "description": "The sasToken required to access _artifactsLocation.  When the template is deployed using the accompanying scripts, a sasToken will be automatically generated. Use the defaultValue if the staging location is not secured."
          },
          "defaultValue": ""
      }
  },

## 3. 




