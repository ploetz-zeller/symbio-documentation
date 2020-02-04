# Intrafind Console Application

## Common information

When an Symbio's Intrafind microservice is connected to a storage, any changes, creations or deletions of object in Symbio will be transmitted to 
the microservice and then to Intrafind. But sometimes, you want to do a full snapshot (full-fetch) of all storage's data from scratch with a complete update of Intrafind.
For this case exists the console application.

To be able to use the console application, you need to have a fully setup Intrafind Indexer microservice, connected to at least one storage.

### How to use the console application

For doing a full-fetch , you can use the commandline tool, which you get by the same way you received your II installation package. 
You must adapt its appsettings.json like you did for the II microservice. You can also use the microservice's appsettings.json for the full-fetch commandline tool.

The full-fetch command can then be executed like this (from commandline):

    dotnet.exe Symbio.Service.Intrafind.Console.dll fullfetch -t [database tenant id]

The database tenant id is shown in Symbio's 'storage collection administrative area', select the storage under 'Storages', and press CTRL-ALT-D.
Or you can grab it from the log file.

You must also check Symbio's log files. In case of an unreachable, not running microservice, there will be no entry about this in microservice's log file, of course.
On Symbio's side, log file checking for errors is done in the same way. You check for errors of type ERR or FTL. E.g., the error for a non-reachable microservice would look like this:

    [Error] "Event HTTP request call: The remote server returned an error: (502) Bad Gateway. for URL 'https://localhost:44316/'" [...]

The given URL has to be replaced with the microservice URL, of course. You can filter for this microservice URL to find out errors regarding the microservice in Symbio's logs.

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

Another full-fetch was started while a previously started is still running. There is only one full-fetch per Symbio-tenant allowed.

##### "Starting a crawl session, but no valid SymbioUrl or ApiToken given"

Please check IntrafindIndexer installation and configuration.
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

An unrecoverable fatal error occured during a full-fetch session.
Processing was interrupted, and Intrafind documents and Symbio elements are not in-sync.
Information may be deleted from Intrafind document store, until another full-fetch run completed successfully.

##### "Trying to access SymbioApi with invalid connection data"

Please check IntrafindIndexer installation and configuration. Try to unlink and link again to storage.
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
