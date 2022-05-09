# Dash App Deployment (end-to-end)

## Get started
1. Click to deploy here.
[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://dev.azure.com/batdigital/OneDRA/_build?definitionId=6651)
2. Click `Run pipeline` on top right. 

## This automation template covers:
1. Provisioning of Dash App Cloud Resources (App Service Plan, App Service and Azure Container Registry).
2. Cloud resource provisioned according to standardized naming and tagging convention.
3. Password-less authentication between App Service and ACR using Managed Identity with `ACRPull` role assigned to the newly created App service.
4. App Service configured to pull new images with `latest` tag from the newly created ACR with Continuous Deployment configuration setup.
5. Setting up of Azure Git repo for data scientist for their storage of development code with branch policy configured.
6. An ADO pipeline yaml with proper CI/CD setup are in place when the Git repo is initialized.

## Values provided from pipelines automation:
1. Reduce lead time on infrastructure provisioning and repo initialization
2. Improve consistency of standardization of naming and tagging on infra, folder structure in repo
3. Provide quickstarts that advocates best practice and governance (externalize credential from source code, authenticate password-less within cloud resources)

## Trigger the automation pipeline
An intuitive parameter form-like pop ups before running the pipeline. These information is crucial to ensure the resources provisioned is following as the service request by end markets.

![automation-pipeline.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/dash-acr-webapp/images/automation-pipeline.png)

### Resources Validation with What-If Operation and Approval
While the resources are in creation, there will be ARM template deployment `What-If operation` to preview the changes that will happen in the first stage.

![what-if.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/dash-acr-webapp/images/what-if.png)

Once the changes preview is satisfied, pipeline can be approved to proceed into next step.

![pipeline-approval.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/dash-acr-webapp/images/pipeline-approval.png)

## By the completion of the automation, you will get:
1. Resources created following the configuration, naming and tagging convention as parameter input in the automation pipeline.

![resource-group-deployment.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/dash-acr-webapp/images/resource-group-deployment.png)

2. Managed Identity created with ACRPull role assigned with scope on the newly created ACR and assigned to the App Service.

![managed-identity.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/dash-acr-webapp/images/managed-identity.png)

3. Repository intialized based on the naming convention along with branching policy and CI/CD pipeline yaml in place.

![repo-intialization.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/dash-acr-webapp/images/repo-intialization.png)
