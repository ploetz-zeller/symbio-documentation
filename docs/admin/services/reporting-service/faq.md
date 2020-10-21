# FAQ

- What about Power BI?
  
  --> should be removed from all documents

- What is an "ODS" database?
  
  --> Operational Data Store https://en.wikipedia.org/wiki/Operational_data_store

- How to setup an ODS database?
  
  --> explain

- What are appropriate rights for the IIS Application Pool account used for the Reporting Connector
  
  --> e.g. R/W for logging

- **What to set for "global:sqlCommandExecutionTimeoutInSeconds"?**
  
  This value is typically set to 7200 (i.e. two hours) to ensure that large amounts of CRUD jobs can be executed in one console CRUD command run without getting a SQL Server timeout error.
  If you don't have many CRUD events and/or are running CRUD commands regularly using scheduled tasks (e.g. every hour/every 15 minutes) then you can try to use a lower value for this setting.

- Which connection string is used for what actions?
  - Administrative connection string?
  - Read-only connection string?

  --> see note in Symbio

- How do I monitor the correct operation of the Symbio Reporting system?
  
  - Check Connector logs for errors
  - Check Console logs for errors

- How to start investigation, if I suspect data to be wrong or missing?
  
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