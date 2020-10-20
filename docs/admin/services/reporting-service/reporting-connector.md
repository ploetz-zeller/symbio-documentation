# Reporting Connector 


## Requirements

To set up the **Reporting Connector** you will need either an IIS installation with a current version of the ASP.NET Core Hosting package installed or an Azure App Service ready for deployment. In both cases the service will need access to Symbio, SSRS and the ODS database. It must also be reachable by the server side component of Symbio.

## Installation

#### Reporting Connector on IIS
1. Create a directory to host the files of the connector service, e.g. _C:\SymbioServices\Reporting\Connector_
2. Copy all files and folders of the service into this directory
3. In IIS Manager:
    1. Create a new Application pool (No Managed Code/Integrated) and assign a user account with appropriate rights to the created directory
    2. Create a new Application using the created pool and selecting the created directory
    3. Note the resulting URL (composed of website binding URL and the selected alias/path of the new application)
4. Configure the Connector by editing its appsettings.config files 
5. Test connection to service by navigating to the noted URL

#### Reporting Connector as Azure App Service

1. Deploy the service package
2. Ensure that the resulting web.config is not automatically set to the version V2 of the AspNetCoreModule
3. Note the URL of the deployed service
4. Configure the Connector by editing its app service settings
5. Test connection to service by navigating to the noted URL


## Configuration


The Connector service has several values that need to be configured for it to function properly. These values can be set in its appsettings.config file (IIS) or the app service settings of Azure.

| Setting | Meaning |
| ------- | ------- |
| security:authToken | The freely defineable token string that Symbio needs to provide to be allowed access to this connector service instance. |
| configStore:type | Either _SqlServer_ or _AzureTableStorage_; the type of database server to connect to. |
| configStore:table | The name of the table to manage connector service settings in, e.g. _ReportingConfig_. |
| configStore:connection | The connection string to use for connecting to a database to store the settings table in. DBO rights are needed to create the table. |
| global:ssrsEndpointUrl | The SSRS reporting service endpoint URL noted during SSRS setup with _/ReportService2010.asmx_ appended, e.g. _https://example.com/ReportServer/ReportService2010.asmx_. |
| global:ssrsUserName | The name of a user which has management access to the SSRS root folder path given above. |
| global:ssrsPassword | The password of the user named above. |
| global:ssrsRootFolderPath | The SSRS root folder path for this connector instance as noted during SSRS worksapce template setup, e.g. _SymbioReporting_.  |
| global:templateName | The name of the template folder in the root path given above as noted during SSRS workspace template setup, e.g. *_Template*. |
| global:sqlCommandExecutionTimeoutInSeconds | The SQL command execution timeout in seconds, e.g. 7200. |



