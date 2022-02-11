# Azure Kubernetes Service (AKS)

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/CredScanResult.svg)

![Bicep Version](https://azurequickstartsservice.blob.core.windows.net/badges/quickstarts/microsoft.kubernetes/aks/BicepVersion.svg)

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fdse-customized-templates%2Fmicrosoft.kubernetes%2Faks%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fdse-customized-templates%2Fmicrosoft.kubernetes%2Faks%2Fazuredeploy.json)

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

## Additional resource of `Microsoft.ContainerService/managedClusters/agentPools`

As mentioned [here](https://docs.microsoft.com/en-gb/azure/aks/use-multiple-node-pools#manage-node-pools-using-a-resource-manager-template), the additional block of `agentPools` are used to update node pool on existing AKS after the creation of initial node pool. 
