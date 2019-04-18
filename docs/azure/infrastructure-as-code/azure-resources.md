# Azure resources

Azure resources are the types of infrastructure that can be added to your Azure instance. You can structure your resources on Azure into Resource groups to show resources that are supposed to belong together.

## Working with resources 
Existing resources can be extracted into resource templates. This can help to use existing resources from your current Azure portal. Important to note: Even if you select only one resource, the whole resource group is ALWAYS extracted in it’s entirety, and not only the selected resource.

Some resource groups in the current PZ Azure portal has been grouped into one resource group. This will change going forward, where each micro-service as an example will have it's own resource group.

One hint on the Microsoft page is to arrange resources with the same life-cycle in a resource group.

Adding tags to your resources will help you to organize your resources. It can also be used to differentiate the resource for billing purposes.

Most types of resources are supported. You can create the storage space for an Azure table, but not the table itself as an example. They are working on it and it may become available soon.

Resources across different resource groups can access each other and does not need to be in only one resource group.

You can move resources between existing resource groups (with a few exceptions).

## Resource types:
* Virtual Networks
* Virtual machines
* Web Apps
* Storages
* Servers
* Databases
* More than 100 different resources are available

![Azure resources](media\resourceStructure.png "Azure resources")

[Microsoft learning page - Resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview "Microsoft Resources Learning page")
