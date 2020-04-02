# Logging

## Common information

Serilog is used for logging. Configuration is done in appsettings.json. 
See Serilog's [documentation](https://github.com/serilog/serilog/wiki/Configuration-Basics) for further information.
The default settings will create a Logs sub-folder in IntrafindIndexer's application path and store there 
log-files on a per-day file basis. The default log file name pattern is 'symbio-service-intrafindindexer-log-YYYYMMDD.txt'.
Default log level is INFORMATION.
Log level DEBUG gives a detailed information in case of problems.
Log level VERBOSE is really for tracing down problems and may slow down the hosting system
 and flood the storage device containing the log files for large databases. You should not leave it enabled on a customer's machine unsupervised.

A live-view of today's current log file is possible by

    powershell gc -wait [logfile]

Please see Serilog's documentation on how to set up notification for log file errors. E.g., e-mail notification can be done by the [e-mail sink](https://github.com/serilog/serilog-sinks-email).

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
