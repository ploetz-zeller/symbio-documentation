# Reporting Connector & Console - Configuration

## Requirements

Connector / Console is already [set up](deploy-connector-console.md).

## Configuration

### Reporting Connector<a name="connector"></a>

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
| global:templateName | The name of the template folder in the root path given above as noted during SSRS workspace template setup, e.g. __Template_. |
| global:sqlCommandExecutionTimeoutInSeconds | The SQL command execution timeout in seconds, e.g. 7200. |

### Reporting Console<a name="console"></a>

Currently, no special configuration is necessary.
