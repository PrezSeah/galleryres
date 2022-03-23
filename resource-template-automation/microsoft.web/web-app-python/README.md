# Create a web app on Azure with Python 3.7 enabled

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.web%2Fweb-app-python%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.web%2Fweb-app-python%2Fazuredeploy.json)

This template creates a web app on azure with Python 3.7 enabled allowing you to run Python applications in Azure. 

The web app with Python is an app service that allow you to deploy your Django or Flask website. This will deploy a free tier Linux App Service Plan where you will host your App Service.

If you are new to Azure App Service, see:

- [Azure App Service](https://azure.microsoft.com/services/app-service/web/)
- [Template reference](https://docs.microsoft.com/azure/templates/microsoft.web/allversions)
- [Quickstart templates](https://azure.microsoft.com/resources/templates/?resourceType=Microsoft.Compute&pageNumber=1&sort=Popular&term=web+apps)

If you are new to template deployment, see:

- [Azure Resource Manager documentation](https://docs.microsoft.com/azure/azure-resource-manager/)

- [Creating a Python App in Azure App Services](https://docs.microsoft.com/azure/app-service/containers/quickstart-python?tabs=bash)

### Prerequisites

If you have already a Linux App Service Plan, you will have to deploy the new web app into the same resource group that the other web app is. That's because Student accounts has a limit of only 1 free tier Linux app service plan.

Tags: Azure4Student, appServices , flask, linux, Intermediate


