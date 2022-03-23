# Assign a Role at Subscription Scope

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fsubscription-deployments%2Fsubscription-role-assignment%2Fazuredeploy.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=/https%3A%2F%2Fraw.githubusercontent.com%2FPrezSeah%2Fgalleryres%2Fmain%2Fresource-template-automation%2Fsubscription-deployments%2Fsubscription-role-assignment%2Fazuredeploy.json)   

This template is a subscription level template that will assign a role at subscription scope.

*NOTE: Role assignments use a GUID for the name, this must be unique for every role assignment on the subscription.  The roleAssignmentName parameter is used to seed the guid() function with this value, change it for each deployment.  You can supply a guid or any string, as long as it has not been used before when assigning the role to the subscription.*
