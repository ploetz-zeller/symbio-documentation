# Symbio Reporting

## Requirements

[Reporting Connector](reporting-connector.md) is already set up.

## Short Overview of Configuration steps

1. Create and configure a report pool if it does not exist. You may reuse an existing report pool for different storages.
1. Assign a report pool to a storage. After successful assignment, you can find the authorization token on the admin page's 'Automation' tile.
1. Activate those reports from the report set you want to use in your connected storage.

## Explanation
### Report Pool

In Symbio follow these steps to create and configure a report pool:

1. Login as an admin user to the _sysadmin collection_
2. Switch to _External systems_
3. Select type _Report pool_ and name your new report pool appropriately
4. Edit the settings of the new report pool as described below

![](media/config-symbio-1.png)

| Setting | Meaning |
| ------- | ------- |
| Service endpoint url | Enter the URL of the connector service as noted during its setup. |
| Authentication token | Enter the security:authToken that was defined in the connector service's settings. |
| Administrative connection string | Enter a connection string to the ODS database that allows full access to the database. e.g. _Server=localhost;Database=ODS;User ID=ODSWriter;Password=ODSWriterPwd_|
| Read-only connection string | Enter a connection string the the ODS database that allows read-only access to the database. e.g. _Server=localhost;Database=ODS;User ID=ODSReader;Password=ODSReaderPwd_|
| SSRS root folder path | The SSRS root folder path for this connector instance as noted during SSRS worksapce template setup, e.g. SymbioReporting. |
| Report template folder | The name of the template folder in the root path given above as noted during SSRS workspace template setup, e.g. Template. |
| SSRS enabled | check this option |

### Connecting a storage to a report pool

In Symbio follow these steps to connect a storage to a report pool:

1. Login as an admin user to the _Collection_ where the storage is located
2. Switch to _Storages_
3. Select the storage to connect to a Report pool
4. Select the desired _Report pool_ from the drop down

![](media/config-symbio-2.png)

This will trigger the creation of reports in Symbio (if SSRS has been enabled on the pool, and the workspace contains reports to link to).

#### IsPermittedEverywhere
Please keep in mind that you can set the Symbio authorization token to be permitted everywhere,
with end end date until this permission set is valid.
This permission set may be valid for operations or objects it was not intended for,
and may have an impact on Symbio's behaviour.

![screen](./media/is-permitted-everywhere.png)

### Activating reports in a storage

In Symbio follow these steps to activate reports in a storage:

1. Login as an admin user to the _storage_
2. Switch to the _admin area_ of the storage
3. Select _Reporting_ under _Configure_
4. Select the report that should be activated and the mark the _Activated_ checkbox

![](media/config-symbio-3.png)

The report is now available in the reporting dropdown:

![](media/config-symbio-4.png)
