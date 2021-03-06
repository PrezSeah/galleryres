# Databricks workspaces

## Get started
1. Click to deploy here.
[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://dev.azure.com/batdigital/OneDRA/_build?definitionId=7017)
2. Click `Run pipeline` on top right. 

## This automation template covers:
1. Provisioning of Databricks workspaces.
2. Cloud resource provisioned according to standardized naming and tagging convention.

## Values provided from pipelines automation:
1. Reduce lead time on infrastructure provisioning
2. Improve consistency of standardization of naming and tagging on infra

## Trigger the automation pipeline
An intuitive parameter form-like pop ups before running the pipeline. These information is crucial to ensure the resources provisioned is following as the service request by end markets.

![automation-pipeline.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/databricks-workspace/images/automation-pipeline.png)

### Resources Validation with What-If Operation and Approval
While the resources are in creation, there will be ARM template deployment `What-If operation` to preview the changes that will happen in the first stage.

![what-if.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/databricks-workspace/images/what-if.png)

Once the changes preview is satisfied, pipeline can be approved to proceed into next step.

![pipeline-approval.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/databricks-workspace/images/pipeline-approval.png)

## By the completion of the automation, you will get:
1. Resources created following the configuration, naming and tagging convention as parameter input in the automation pipeline.

![resource-group-deployment.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/databricks-workspace/images/resource-group-deployment.png)
