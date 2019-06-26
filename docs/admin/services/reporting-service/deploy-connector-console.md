# Reporting Connector & Console - Installation

## Requirements

To set up the **Reporting Connector** you will need either an IIS installation with a current version of the ASP.NET Core Hosting package installed or an Azure App Service ready for deployment. In both cases the service will need access to Symbio, SSRS/Power BI, and the ODS database. It must also be reachable by the server side component of Symbio.

To set up the **Reporting Console** you will need a machine with a current version of the .NET Core runtime installed. This machine needs access to Symbio and the ODS database.

## Setup 

### Reporting Connector on IIS

1. Create a directory to host the files of the connector service, e.g. _C:\SymbioServices\Reporting\Connector_
2. Copy all files and folders of the service into this directory
3. In IIS Manager:
    1. Create a new Application pool (No Managed Code/Integrated) and assign a user account with appropriate rights to the created directory
    2. Create a new Application using the created pool and selecting the created directory
    3. Note the resulting URL (composed of website binding URL and the selected alias/path of the new application)
4. Configure the [Connector](config-connector-console.md#connector) by editing its appsettings.config files 
5. Test connection to service by navigating to the noted URL

### Reporting Connector as Azure App Service

1. Deploy the service package
2. Ensure that the resulting web.config is not automatically set to the version V2 of the AspNetCoreModule
3. Note the URL of the deployed service
4. Configure the [Connector](config-connector-console.md#connector) by editing its app service settings
5. Test connection to service by navigating to the noted URL

### Reporting Console on a Windows machine

1. Create a directory to host the files of the console application, e.g. _C:\SymbioServices\Reporting\Console_
2. Copy all files and folders of the application into this directory
3. Configure the [Console](config-connector-console.md#console) by editing its appsettings.config files
