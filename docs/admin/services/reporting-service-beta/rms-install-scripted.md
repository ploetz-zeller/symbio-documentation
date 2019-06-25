# RMS Scripted Installation

## Requirement

- Powershell Version 5.0 or higher. Download [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395)
- [.NET Core Windows Server Hosting Package](https://www.microsoft.com/net/download/dotnet-core/2.1)
- Download the Install.ps1 file from the [Operations Page](http://operations.symbioworld.com/).
- Download the symbio-service-reporting.parameters.json file from the [Operations Page](http://operations.symbioworld.com/).

Open and edit the symbio-service-reporting.parameters.json file.
Replace the settings with your own values:

## Parameters

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
| IISSettings.ApplicationPoolUser| The name of the domain user, with right to the ssrs, that is to be used as the service identity.
| IISSettings.ApplicationPoolPassword | The password of the specified application pool user. If no password is given and the IdentityType is set to 3, the script will prompt for the password during installation.
| IISSettings.Bindings | List of bindings
| IISSettings.Bindings.Protocol | The protocol contains *http* or *https*
| IISSettings.Bindings.IPAddress | The IP address to use. Default is * for all IP addresses.
| IISSettings.Bindings.Port | The port is an integer. The default port for *http* is 80 and for *https* 443.
| IISSettings.Bindings.HostName | The hostname for the binding. Use * for all hostnames.
| IISSettings.Bindings.CertificateHash | The thumbprint hash of the certificate you want to use. ([This is how you get the fingerprint.](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate)) This parameter is optional if you maintain the CertificateCN.
| IISSettings.Bindings.CertificateCN | The CN of the certificate. This can be found in the details of the certificate as field `Subject`.
| IISSettings.Bindings.SslFlag | The optional parameter SslFlag is responsible for activating SNI in the binding. Set 1 to activate SNI ([What is SNI?](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-server-name-indication-sni-ssl-scalability)).

---

## AppSettings

| Name | Description
| --- | --- |
| Server| Name or address including port of your database server
| Database | The name of your RMS database
| ConfigStoreTableName | The name of you existing configtable

---
If all settings are corretly set, please start a new powershell console as administrator, change into the directory of the downloaded script, and run the following command:

```PowerShell
.\Install.ps1 -ParametersFile .\symbio-service-reporting.parameters.json
```

*`nice to know`*

*- If you use a domain user. You must write [server] \\\\\\\\ [user].*

*- You can omit the specification of the Files parameter by renaming symbio-service-ssrs-reporting.parameters.json to parameter.json. The script detects the JSON itself, if they are in the same folder.*

*- If you already operate a fully configured IIS on the target machine, you can use the switch `-WithoutIIS`. This turns off the checking and installation of the IIS components.
This is only recommended if you have already executed the script at least once with a successful IIS configuration.*

---

## Finalizing

When the installation script is successfully completed, continue with the [configuration](./RMSConfiguration.md#reporting-micro-service-and-config-store) of your RMS.