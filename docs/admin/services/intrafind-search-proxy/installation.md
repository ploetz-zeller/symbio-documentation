# Installation

## Requirements

- OS-Version: Windows Server 2012 or higher
- IIS-Version: 7.5 or higher
- SQL-Server-Version: 2016 or higher
- .NET Core Version: 3.1
- .NET Core Windows Server Hosting-Version: 3.1
- Processors: 4 or higher
- Memory: 4 or higher

### Additional requirements

- The Intrafind SearchProxy (IFSP) user set up in/for IIS has to own appropriate rights to access its files and the SQL database

## Manual Installation

### Setting up a new site on IIS

1. Download and install [.NET Core Windows Server Hosting Bundle 3.1](https://dotnet.microsoft.com/download/dotnet-core/thank-you/runtime-aspnetcore-3.1.1-windows-hosting-bundle-installer)
1. Download the IFSP artifact or ask Symbio support for the IFSP package
1. Extract it to the installation folder of the service
1. Create a new site in IIS (bindings depending on you infrastructure)
1. Adjust the AppPool Basic Settings: No Managed Code

### Setting up an SQL database

1. Create a database on your SQL Server to hold the IFSP configuration data, e.g. "SqlServerConfigStore"
1. Create an SQL login with owner rights for the created database
1. Set the correct SQL connection string to the created database in IFSP's appsettings.json
1. Set TrustServerCertificate=True in the connection string if you are using a self-signed or no certificate

## Scripted Installation

### Preparations

- Ensure Powershell Version 5.0 or higher is available. Download [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395)
- Download and install [.NET Core Windows Server Hosting Bundle 3.1](https://dotnet.microsoft.com/download/dotnet-core/thank-you/runtime-aspnetcore-3.1.1-windows-hosting-bundle-installer)
- Download the Install.ps1 file from the [Operations Page](http://operations.symbioworld.com/).
- Download the symbio-service-searchproxy-intrafind.parameters.json file from the [Operations Page](http://operations.symbioworld.com/).
- Ensure a database for configuration information is available (see *Setting up an SQL database* above)

### Edit the Parameters.json file

| Name | Description |
| --- | --- |
| SourcePath | The download or local path of the installation package (zip file).
| BaseTargetPath | The local root directory path for IIS websites
| BaseBackupPath | The local directory path to backup your existing service
| InstanceName | The name of the main instalations directory
| IISSettings.Enabled | *true*, if an IIS website should be created, otherwise *false*.
| IISSettings.SiteName | The name of the IIS Website.
| IISSettings.ManagedRuntimeVersion | The managed runtime version. This value should not be changed. Leave the value empty (no managed runtime).
| IISSettings.IdentityType | The [identity type](https://docs.microsoft.com/en-us/iis/configuration/system.applicationhost/applicationpools/add/processmodel).
| IISSettings.ApplicationName | The name of the IIS application if applicable.
| IISSettings.ApplicationPoolName | The name of application pool.
| IISSettings.ApplicationPoolUser| The name of the domain user, with rights to access the SQL database; it will be used as the service identity.
| IISSettings.ApplicationPoolPassword | The password of the specified application pool user. If no password is given and the IdentityType is set to 3, the script will prompt for the password during installation.
| IISSettings.Bindings | List of bindings
| IISSettings.Bindings.Protocol | The protocol contains *http* or *https*
| IISSettings.Bindings.IPAddress | The IP address to use. Default is * for all IP addresses.
| IISSettings.Bindings.Port | The port is an integer. The default port for *http* is 80 and for *https* 443.
| IISSettings.Bindings.HostName | The hostname for the binding. Use * for all hostnames.
| IISSettings.Bindings.CertificateHash | The thumbprint hash of the certificate you want to use. ([This is how you get the fingerprint.](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate)) This parameter is optional if you maintain the CertificateCN.
| IISSettings.Bindings.CertificateCN | The CN of the certificate. This can be found in the details of the certificate as field `Subject`.
| IISSettings.Bindings.SslFlag | The optional parameter SslFlag is responsible for activating SNI in the binding. Set 1 to activate SNI ([What is SNI?](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-server-name-indication-sni-ssl-scalability)).

#### AppSettings

| Name | Description
| --- | --- |
| [SERVER] | Name or address (including the port) of your database server
| [CONFIG-DB] | The name of your configuration database
| [CONFIG-TABLE-NAME] | The name of the (already existing) configuration table

### Running the Script

If all settings are corretly set, please start a new powershell console as Administrator, change into the directory of the downloaded script, and run the following command:

```PowerShell
.\Install.ps1 -ParametersFile .\symbio-service-searchproxy-intrafind.parameters.json
```

*`nice to know`*

*- If you use a domain user. You must write [server]\\[user].*

*- You can omit the specification of the Files parameter by renaming symbio-service-searchproxy-intrafind.parameters.json to parameter.json. The script detects the JSON itself, if they are in the same folder.*

*- If you already operate a fully configured IIS on the target machine, you can use the switch `-WithoutIIS`. This turns off the checking and installation of the IIS components.
This is only recommended if you have already executed the script at least once with a successful IIS configuration.*

## Conclusion

You have now set up the IFSP. The next step is configuring it in Symbio.
