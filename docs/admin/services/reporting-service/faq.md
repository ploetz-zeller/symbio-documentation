# FAQ

## What is an "ODS" database?

**ODS** stands for **Operational Data Store**, see https://en.wikipedia.org/wiki/Operational_data_store for details.

Symbio Reporting uses the ODS database to store its data in a way friendly to reporting while Symbio Core has its data organized in a different way to better support its interactive and presentational usage patterns.

The ODS database contains a snapshot of a past state of Symbio Core. There are several mechanisms to keep it in synch so it is not older than a specified time span.

## How to setup an ODS database?
  
The Symbio Reporting ODS database is a normal SQL Server database independent of other Symbio databases and SSRS' ReportServer databases. One ODS database can be used for several Symbio storages as the data within is separated by tenant.

For administrative and read-only connection strings the creation of corresponding users is advised:
- **OdsReader** for the read-only connection string should be a member of the role *db_datareader*
- **OdsWriter** for the administrative connection string should be a member of the roles *db_datawriter* and *db_owner*

## How to keep the ODS database and Symbio Core in synch?

The **Reporting Connector** listens to change events sent by Symbio Core. These are stored in the ODS database for later processing.

The **Reporting Console** provides two mechanisms to update the ODS database:

- **Fullfetch** creates a new snapshot of Symbio Core and updates the ODS database to that snapshot. This is typically done once a week during the weekend, either triggered manually or scheduled for automatic execution using a task scheduler.
- **CRUD** collects the change events stored in the ODS database and applies them to the stored data. This is typically scheduled to be executed once per hour using a task scheduler.

## What are appropriate rights for the IIS Application Pool account used for the Reporting Connector
  
The application pool account needs to be able to read and execute the content of the app's directory. Additionally, it needs to be able to write log files. Setting "Full Access" to the app's directory and inheriting that to all files and sub folders will ensure all necessary permissions are available.

## What to set "global:sqlCommandExecutionTimeoutInSeconds" to?
  
This value is typically set to 7200 (i.e. two hours) to ensure that large amounts of CRUD jobs can be executed in one console CRUD command run without getting an SQL Server timeout error.

If you don't have many CRUD events and/or are running CRUD commands regularly using scheduled tasks (e.g. every hour/every 15 minutes) then you can try to use a lower value for this setting.

## Which connection string is used for what purpose?

### Administrative connection string

The administrative connection string will be used for DB operations and manipulations, e.g. a fullfecth. DBO rights are required.

### Read-only connection string

The read-only connection string will be used for read access by reports. Only read permissions are required. 

## How do I monitor the correct operation of the Symbio Reporting system?

**Reporting Connector** and **Reporting Console** write log files of their operation. These files should be checked regularly for errors.

## How to start investigation, if I suspect data to be wrong or missing?
  
  - On the Admin page, is there a valid token for the Reporting system (under data-rest api)
    - Report Pool entry correct - compare with sysadmin/external systems, name and id of report pool (Ctrl+Alt+D)
    - Test with Postman, URL (https://localhost/Symbio/(collection)/(storage)/_api/rest/info/reporting), Token
      - example image
    - Is Symbio accessible from the connector server?
  - Test URL of reporting connector (see report pool) - avoid firewall issues e.g.
    - is the URL accessible? from the Symbio server?
    - is the time update on refresh?
    - is the version number correct?
  - Test console fullfetch-open-list (or any any other non-modifying command)
    - can console access Symbio, tenant and token are tested
    - can access ODS DB
  - SSRS website accessible ReportServer & ReportPortal
    - from Symbio server
    - from connector server
    - Template folder not empty
      - Reports can be opened and show something. e.g. hierarchy report (check before stating)
    - ReportPortal contains folder with name = id of report pool (Ctrl+Alt+D)
      - Data Source exists and correctly configured?
      - Reports exist?
  - Symbio Admin Page / Reporting
    - Reports there
    - Reports activated
    - those reports listed on reports page in drop-down
    - compare id of report pool (Ctrl+Alt+D)
  - check Symbio logs
  - check other logs
  - contact support