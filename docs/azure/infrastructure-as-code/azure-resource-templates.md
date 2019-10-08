# Azure resource Templates

Azure templates have been created to enable the creation of a model for the required resources in azure. These templates can be managed as a separate project in your current Solutions in Visual Studio.

* Templates are JSON based
* Creating templates
  * Templates of current environments can be extracted
  * Templates for common resource types can be found within Visual Studio by adding a resource and selecting the type or they can be found on the portal and used as a base to create your own.
  *  Not all resources are on the list in VS and it is advisable to search the repository on Github if you do not find what you are looking for.
* Editing templates
  * Azure portal Build your own template in the editor when adding a resource
  * Visual studio code
  * Visual studio
  * Extensions for Visual Studio + VS Code exist
* Can use multiple linked JSON files for different resources
* Templates can contain available functions to ensure an unique name as an example


![IaC overview](media\resourceTemplates.png "IaC Overview")

[Microsoft learning page - Resource templates](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-authoring-templates "Microsoft resource templates")

[Azure template repository](https://github.com/Azure/azure-quickstart-templates "Azure template repository")

[Azure template functions](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-template-functions "Azure template functions")
