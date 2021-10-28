# Intrafind Console Application

## Common information

When Symbio's Intrafind Connector service is connected to a storage, any changes, creations or deletions of elements in Symbio will be transmitted to the service and then to Intrafind.
Sometimes, you want to do a full snapshot (full-fetch) of all storage data from scratch with a complete update of Intrafind.
That's the use case of the console application.

To be able to use the console application, you need to have a fully setup Intrafind Connector service, connected to at least one storage.

_The full-fetch operation of the console application is usually an operational aspect managed by Symbioworld._

### How to use the console application

For doing a full-fetch, you will use the console application. 
Its appsettings.json needs to reflect the basic settings applying to the Intrafind Connector instance you want to manage.

The full-fetch command can then be executed like this:

    dotnet.exe Symbio.Service.Intrafind.Console.dll fullfetch -t [database tenant id]

The database tenant id is shown in Symbio's 'storage collection administrative area':
select the storage under 'Storages', and press CTRL-ALT-D.

Any connection issues will be either logged in the console application or in Symbio.
Please contact Symbio Support if you encounter any problems.

### Sample fullfetch log entries

<pre><code>
2019-02-18 15:53:53.808 +01:00 [INF] Crawling started for tenant database '21cea141-b334-4c72-9b0c-bb84b5465a7b'...
2019-02-18 15:53:54.847 +01:00 [INF] #Documents known to Intrafind: 338
2019-02-18 15:53:58.847 +01:00 [INF] 		 Found valid/released 'mainProcess', version 2.0, id '0d12c107-5b73-4afa-9636-cbc1a43f505e' and versionId '5a1db2fc-11ae-4f00-9cb5-5899fc747167'
...
2019-02-18 15:54:37.321 +01:00 [INF] Count of all known documents to Intrafind: 338; thereof existing only in Intrafind: 0
2019-02-18 15:54:37.321 +01:00 [INF] Deleted 0 out of 0 obsolete Intrafind documents.
2019-02-18 15:54:37.322 +01:00 [INF] 21cea141-b334-4c72-9b0c-bb84b5465a7b: Crawling finished after 00:00:43.5127593'
</code></pre>

Each Symbio element eligible for indexing in Intrafind is logged by 'Found valid/released [...]'

## Common log file entries

#####  "Crawling session is already running"

Another full-fetch was started while a previously started one is still running. There is only one full-fetch per Symbio-tenant allowed.

##### "Starting a crawl session, but no valid SymbioUrl or ApiToken given"

Please check Intrafind Connector service installation and configuration.
Provide valid Symbio URL.
Try to unlink and link again to storage.
Check microservice's database settings.

## Errors

##### "Event 'Elements have changed' but connection-state is invalid: [ConnectionState]. Stopping further processing."

The microservice received a changed-event, but for given reason Symbio's REST API is not available.
Check 'external system configuration'.
Try to unlink and re-link again. Check for previous errors in log file.

## Fatal, unrecoverable errors

##### "Unexpected exception during crawling occurred, stopping."

An unrecoverable fatal error occurred during a full-fetch session.
Processing was interrupted, and Intrafind documents and Symbio elements are not in-sync.
Information may be deleted from Intrafind document store, until another full-fetch run completed successfully.

##### "Trying to access SymbioApi with invalid connection data"

Please check Intrafind Connector service installation and configuration. Try to unlink and link again to storage.
Check microservice's database settings.

##### "Token role invalid, please check Symbio configuration"

Please check access token configuration in Symbio. Is a proper token role in 'external system configuration' selected?

##### "No activated token role given, please check Symbio configuration"

Please check access token configuration in Symbio. Is a proper token role in 'external system configuration' selected?

##### "Could not parse custom attribute '[name]' from ExternalSystem data"

Please check mentioned custom attribute in 'external system configuration'.

##### "Token role is '[...]', need at least 'Viewer'-role. Please check Symbio configuration"

Token role 'access' was given.
Please check access token configuration in Symbio. Is a proper token role in 'external system configuration' selected?
