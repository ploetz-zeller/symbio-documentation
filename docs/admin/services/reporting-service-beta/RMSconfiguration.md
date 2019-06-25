# Configuration

## Configuration for the RMS

### Reporting micro service and config store

1. The reporting micro service has to deployed on an accessable machine to ensure proper communication to both sides, Symbio on the one hand and the used reporting services (e.g. SSRS) on the other hand.
2. Navigate to the installation directory of your RMS and open the appsettings file. Now edit the connection string to your _RMS-ConfigStore_ and the _ConfigStoreTableName_
    ```json
    {
      "ConnectionStrings": {
      "ConfigStoreConnection": "Server=[SERVER];Database=[CONFIG-DATABASE];Trusted_Connection=True;"
    },
    "ConfigStoreTableName": "[CONFIG-TABLE-NAME]",
    ```
3. Create the _RMS-ConfigStore_ database. Use the [CONFIG-DATABASE] name stored in the appsettings connection string.
4. The config store table itself _ConfigStoreTableName_ has to be maintained with some settings to ensure correct functionality, e.g. the authentication token mentioned above.  After maintaining the values, the table should look like this.

    ![Config store configuration](media/config-store.png)

| Key        | Value |
| ------------- |-------------
| authToken     | _The token with which Symbio authenticates itself to the Microservice (This value is Custom, here you can use whatever you like)_
| SsrsSettings.SoapEndpointUrl | *`https://HOST_NAME:HOST_PORT/REPORT_SERVER_NAME/reportService2010.asmx`*
| SsrsSettings.SourceFolder | _The name of the source folder in the SSRS. The default is _Template_
| SsrsSettings.RootPath | _The root path for the reports. The default is /_
| SsrsSettings.SoapDomain | _Credentials: domain of the user to use for the datasource connection (Binding entry if the connection string in Symbio uses Integrated Security)_
| SsrsSettings.SoapUsername | _Credentials: username to use for the datasource connection (Binding entry if the connection string in Symbio uses Integrated Security)_
| SsrsSettings.SoapPassword | _Credentials: password of the user to use for the datasource connection (Binding entry if the connection string in Symbio uses Integrated Security)_
| StillAliveCron | _Optional parameter that ensures AlwaysOn. Recommended for OnPrem installations. Cron value indicates time until the next ping. (*/1 * * * * => Means a ping every minute.)_

### Last check

Open a browser and navigate to your Microservice URL.
If your service is configured correctly, you will see a page with a simple login dialog.

If an error is displayed on the website, check the configuration and look it up in [troubleshooting](./troubleshooting.md#rms-troubleshooting) of your RMS.

---

## Configuration in Symbio

### External System/Report Pool

1. To configure the report pool and therefore the micro service navigate to the _sysadmin/_admin_ level and choose the external systems.
2. Select the type _Report Pool_ and create a new one. Provide the corresponding settings.

    ![External system configuration](media/external-system.png)

    * **_URL_**: The url is the concrete to url to the endpoint of the reporting microservice. On a local machine this could be e.g. *`http://localhost:64689/`*
    * **_Authentication token_**: For basic authentication provide a token, which can be an arbitrary string. This token is used to authenticate symbio against the micro service.
      * _NOTE_: This token has to be defined in the _ConfigStoreDatabase_ as well.
    * **_Connection string_**: This is the full connection string to the the database that should be used/setup for the reporting, e.g. (_Server=SERVER_NAME;Initial Catalog=ODS_DATABASE_NAME;Integrated Security=true;MultipleActiveResultSets=False;Encrypt=False;TrustServerCertificate=False;Connection Timeout=30;_). Without Integrated Security, user and password must be entered.
    * **_Cron expression_**: You may provide a valid cron expression to state the interval, in which a full fetch should be performed to update the whole ods database.
    * **_Cron expression (CRUD)_**: You also may provide a valid cron expresson to state the interval, when the aggregated CRUD operations saved in the hangfire queue are send to the database.
    * **_SSRS enabled_**: Activate this setting if you want to use an SSRS.
    * **_Power BI enabled_**: Activate this setting if you want to use Power BI.
    * **_Converter file_**: The attached converter file is executed when the database is connected to the ReportPool.
    * **_Converter file (unlink)_**: The attached converter file is executed when the connection between the database and the ReportPool is removed.

## Linking a storage

If you have successfully setup all the components above, you are ready to use the reporting within a storage. To accomplish this, the following steps have to be done.

1. Navigate to _COLLECTION/_admin_ and choose the storages.
2. Select the storage you wish to connect with a configured report pool.
3. In the detail content you should see the available _ODSReportPools_ in a drop down.
  
    ![External system configuration](media/link-storage-DCConfig.png)

4. By choosing the pool from the selection value the _link_ operation starts. This operation automatically performs the following steps:
    * The micro service is called to to setup the ods database according the settings you made.
    * Symbio will create a token to enable the micro service to run rest api requests against Symbio
    * If linking is successful, Symbio will create web hooks to send events to the micro service, if there are changes to your storage, e.g. insertion of new elements.
    * The micro service will try to retrieve and copy the available reports from the template to the working directory on SSRS site.
    * The micro service will initially perform a full fetch against the Symbio storage to fill the ods database with the available data.
    * After that the micro service will prepare the available reports to be sent to Symbio.
    * When this is done, the status should be successfully changed and all found reports are available are available in Symbio's administration area in _Reports_.
5. You are now ready to use the reports e.g. in the report widgets and show them in the configurable element posters.