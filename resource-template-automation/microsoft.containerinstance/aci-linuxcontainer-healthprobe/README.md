# Azure Container Instances

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.containerinstance%2Faci-linuxcontainer-healthprobe%2Fazuredeploy.json)  
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fmicrosoft.containerinstance%2Faci-linuxcontainer-healthprobe%2Fazuredeploy.json)

This template demonstrates a simple use case for health probe of [Azure Container Instances](https://docs.microsoft.com/en-us/azure/container-instances/). The container will be restarted after it runs for 30 seconds, because the file /tmp/healthy is deleted.


