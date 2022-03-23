# Azure Machine Learning ARM Template Automated Deployment with NewRelic Setup
This automation template covers:
1. Provisioning of prerequisite resources for Azure Machine Learning (AML) Workspace and AML Workspace itself - configuration of the infrastructure such as naming, tagging, location, SKU can be done in the pipeline.
2. Cloud resource provisioned according to standardized naming and tagging convention.
3. NewRelic installation setup script at AML compute instance.

## Trigger the automation pipeline
An intuitive parameter form-like pop ups before running the pipeline. These information is crucial to ensure the resources provisioned is following as the service request by end markets.

![automation-pipeline.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/aml-newrelic/images/automation-pipeline.png)


### Resources Validation with What-If Operation and Approval
While the resources are in creation, there will be ARM template deployment `What-If operation` to preview the changes that will happen in the first stage.

![what-if.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/aml-newrelic/images/what-if.png)

Once the changes preview is satisfied, pipeline can be approved to proceed into next step.

![pipeline-approval.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/aml-newrelic/images/pipeline-approval.png)

## By the completion of the automation, you will get:
1. Resources created following the configuration, naming and tagging convention as parameter input in the automation pipeline.

![resource-group-deployment.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/aml-newrelic/images/resource-group-deployment.png)

2. NewRelic setup at Azure Machine Learning compute instance.

![newrelic.png](https://github.com/PrezSeah/galleryres/raw/main/resource-template-automation/dse-customized-templates/aml-newrelic/images/newrelic.png)

## Get started
To get started, click [Quickstart using Azure Pipelines](https://dev.azure.com/batdigital/OneDRA/_build?definitionId=6805).