# Azure Container Service (AKS)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.kubernetes%2Faks%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.kubernetes%2Faks%2Fazuredeploy.json)

## Deployment

This template deploys an **AKS cluster**. To learn more about how to deploy the template, see the [quickstart](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-rm-template) article.

For information about how to deploy an AKS cluster using Azure CLI, see the [quickstart](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough) article.

## Keys

To use keys stored in `keyVault`, replace `"value":""` with a reference to `keyVault` in the parameters file. For example:

```json
"servicePrincipalClientSecret": {
  "reference": {
    "keyVault": {
      "id": "<specify Resource ID of the Key Vault you are using>"
    },
    "secretName": "<specify name of the secret in the Key Vault to get the service principal password from>"
  }
}
```
