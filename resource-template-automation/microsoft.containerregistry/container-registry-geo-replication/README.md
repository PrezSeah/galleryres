# Azure Container Registry with Geo-replication

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.containerregistry%2Fcontainer-registry-geo-replication%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.containerregistry%2Fcontainer-registry-geo-replication%2Fazuredeploy.json)

This template deploys an Azure Container Registry with [geo-replication enabled](https://docs.microsoft.com/azure/container-registry/container-registry-geo-replication). Azure Container Registry is a PaaS offer for creating your own Docker image registry.

To learn more about how to deploy the template, see the [quickstart](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-geo-replication-template) article.

`Tags: Azure Container Registry, Docker`

## Solution overview and deployed resources

The following resources are deployed as part of the solution. Note the Azure Container Registry is set to **Premium** sku which is required to support Geo-Replication.

- **Azure Container Registry**: Docker image registry
- **Geo-Replicated registry**:  Docker image registry replication

## Login to your registry

Follow [this documentation](https://docs.microsoft.com/azure/container-registry/container-registry-authentication) to authenticate your docker client to your container registry.

## Push images to your registry

For pushing docker images on your registry, follow [this documentation](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-docker-cli).
