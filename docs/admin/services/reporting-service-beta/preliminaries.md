# Preliminaries

You should be sure that the machines are prepared for using all required components.

## Symbio

Please refer to the Symbio manuals to set up Symbio, if not already happened.

## Reporting Micro Service (RMS)

### System Requirements RMS

- OS-Version: Windows Server 2012 or comparable/ higher
- Dot Net Core Versions: 2.1.3 or comparable/ higher
- IIS-Version: 7.5 or comparable/ higher
- Processors: 4 or higher
- Memory: 4 or higher

### Required Software RMS

- SQL-Server 2016 or higher
- IIS has to be installed, same preliminaries as Symbio
- .NET Core has to be installed ([2.1.4 or later](https://www.microsoft.com/net/download/dotnet-core/2.1))
- .NET Core Windows Server Hosting ([2.1.4 or later](https://www.microsoft.com/net/download/dotnet-core/2.1))

### Other requirements for RMS

- The domain RMS user set up in the IIS must have corresponding rights to the SSRS and, if no second user is used, also to the ODB.
- Optional a second domain user for the OBD connection.
- The installation package that you received, like Symbio, via FTP download.

## SSRS

### Required Software SSRS

- SQL Server Reporting Services for your SQL Server version

### Other requirements for SSRS

- The installation package that you received, like Symbio, via FTP download.