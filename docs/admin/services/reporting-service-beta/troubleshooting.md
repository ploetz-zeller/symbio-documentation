# Troubleshooting

## General

- Ensure that the installation of all the required components was successful
- Symbio has to be configured and running
- Reporting micro service (RMS) has to be configured and running
- SSRS components (modules, service) have to be configured and running
- Ensure that the used user accounts have the appropriate rights to e.g. create folders, database, etc.
- If one service refuses to start in IIS, check the credentials of the user or change the user
- Check your table entries in the ConfigStore for undesired whitespaces which you may have inserted by accident

---

## RMS Troubleshooting

### HTTP Error 500.19 Internal Server Error - Incorrect Config

Open Powershell and navigate to the installation folder of your RMS microservices.
Use the following commands to check that your .Net Core is installed and recognized correctly.

```Powershell
dotnet
```

`If you get an error here, you are missing the .NET Core Windows Server Hosting Package.`

```Powershell
dotnet Symbio.Service.Reporting.RestSync.dll
```

Now open a browser and enter the following URL.

```URL
http://localhost:5000
```

If you now see a page with a simple login dialog, there is an error with the IIS in connection with .Net Core.

To fix this, reinstall or repair the .NET Core Windows Server Hosting Package.

### An error occurred while starting the application

If this error is displayed in the website, there is an error in your appsettings.json.

Navigate to the installation directory of the Microservice and open your appsettings.json. Now check the stored connection string _ConfigStoreConnection_ and the specification _ConfigStoreTableName_

### RMS shows error message in log when activating CLR

- Check the SQL Server version. If this version is 2016, check how current it is.
    If necessary, install the [Cumulative Update 9 for SQL Server 2016](https://support.microsoft.com/en-ca/help/4037357/cumulative-update-9-for-sql-server-2016).
- Try to activate CLR manually.
    ````sql
    EXEC sp_configure 'clr enabled', 1;
        RECONFIGURE;

    EXEC sp_configure 'show advanced options',1;
        RECONFIGURE;

    EXEC sp_configure 'clr strict security', 0;
        RECONFIGURE;
    ````

---

## Symbio Troubleshooting

### Linking/unlinking doesn't work

#### Symbio shows a red error message

- Go to _sysadmin/_admin level and check the configuration of the report pool you want to link
- The endpoint must be properly configured and the reporting micro service (RMS) has to be setup properly and responding
- Also check for missing firewall rules that prevent Symbio from communicating with the RMS and vice versa
- Be sure that you provided the correct authentication token (The value in the report pool and in the ConfigStore have to match)

#### After unlinking the report pool the reports remain in the storage that was unlinked

- When unlinking a report pool all the reports that were created on Symbio side should be deleted
- If this is not the case, it is most likely that you have modified the URL of the reports, so that they no longer include the tenant id key

#### After linking the report pool no reports appear in Symbio

- Check the log of the RMS for errors. It is most likely that the RMS had some problem with retrieving the available reports from SSRS side
- Check the credentials to access the SSRS (e.g. SsrsSettings -> SOAP) in the ConfigStore
- On SSRS side check, if the target folder already exists so that the reports were not copied
- Check all the components mentioned above and verify, that they are running

### Display of reports in Symbio fails

- Check the reports configured in the admin area and verify, that all settings are pointing to the correct urls, especially url and the authentication url
- The tenant id parameter has to be provided in the report url, it should automatically provided, when linking is done
- Check the headers of the reports to have the correct data, e.g. compare it with the token on SSRS side, so that Symbio may communicate with the SSRS
- Verify, that there are no typos, e.g. special characters or incorrect placeholder values
- __NOTE:__ Please be aware, that for proper cross communication Symbio and the SSRS should reside in the same domain. This is important for the certificates you use as much as for the configuration of the report, e.g. *`https://SERVERNAME.DOMAIN/REPORTSERVERNAME...`* for the `URL`.

### Reports show incorrect data

- Be sure to use the latest report files on SSRS side, that are applicable for you
- Observe the RMS log for errors and perhaps have a look at the configured ODS database
- In the ConfigStore check the hangfire tables (Hangfire.Job(s), Hangfire.Set) for scheduled jobs or retries, these could indicate sql remedies
- Check if Symbio is fitting to all the other components regarding the version. In most cases every component should be available in its latest version.

---

## HELP! Everything is messed up and I want to start over clean

### Setup all your components

- Within this manual there are descriptions on how to configure and set up each component. Follow them until everything is set up

### Unlink your database

- If you want a fresh and clean start, it is necessary to unlink your database from the report pool

### Clean existing data preserving created databases

- Stop the RMS on IIS so it can not be reached
- Locate the database used for your ConfigStore
- If you didn't configure a separate Hangfire database, delete all the hangfire tables in the ConfigStore database (Hangfire prefix!)
- If you are afraid of deleting all the tables, set every row in Hangfire.Job to "Failed", where the StateName is "Processing" or "Scheduled", and delete all rows in Hangfire.Set
- Remove all tables of the ODS database you specified **(ATTENTION!*)**
- Browse to your SSRS web portal and check the folder structure
- Inspect the folder prefixed with your report pool id (OriginKey of the report pool you connected in Symbio) for the latest report
- If the reports are outdated, update them or delete the whole folder **(ATTENTION!*)**
- If you have managed all this, restart the RMS and try to link again in Symbio

***NOTE**: Only delete the TenantId prefixed folder, if you are absolutely sure, that no other database currently uses it