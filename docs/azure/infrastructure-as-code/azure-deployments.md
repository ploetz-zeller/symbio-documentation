# Azure deployments

Deployments of infrastructure is going to be included in the pipelines of the application being deployed. This will allow the deployment managers to specify multiple deployments to different Azure portals and sites. This includes the automated deployments. Deploying the infrastructure together with the application(s) that requires the resources. This makes Continuous deployments a reality.

* All deployments are shown in the deployment manager and deployments can be monitored or inspected.
* Can be deployed in the following ways aside from the pipelines:
  * Azure portal
  * Azure Cloud Shell
  * Azure REST API
  * Azure CLI
  * C# code
  * Bash

* Deployment scripts are created when a new "Azure Resource Group" project is added to your Solution. The scripts are also extracted when extracting the resource template on Azure.
* Deployment templates exist on top of the resource templates that enable the Operations team to define all the deployment requirements. This is currently managed through the deployment pipelines in DevOps

![Deployment template structure](media\deploymentTemplateStructure.png "Deployment template structure")

![What is deployed, where](media\whatIsDeployedWhere.png "What is deployed, where")

[Microsoft learning page - Deployment manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/deployment-manager-overview "Microsoft Deployment Manager")
