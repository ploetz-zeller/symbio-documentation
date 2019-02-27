---
uid: uniqueid-install-scripted
---
# Scripted Installation

## Requirement

- Powershell Version 5.0 or higher. Download [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395)
- Download the Install-SymbioWeb.ps1 file from the [Operations Page](http://operations.symbioworld.com/).
- Download the symbio-service-uniqueid.parameters.json file from the [Operations Page](http://operations.symbioworld.com/).
- Open and edit the symbio-service-uniqueid.parameters.json file.

Replace the settings with your own values:
### Parameters:
| Name | Description  |
| ---|---------------------------------------|
| SourcePath | The download or local path of the installation package (zip file).  |
| <a name="TargetPath"></a>TargetPath | The local directory for IIS website  |
| NetFrameworkPath | Der Download oder lokale Pfad des .NetFramework-Installationspakets (exe). |
| IISSettings.Enabled | *true*, if an IIS website should be created, otherwise *false*. |
| IISSettings.SiteName | The name of the IIS Website. |
| IISSettings.ManagedRuntimeVersion | The managed runtime version. This value should not be changed. Leave the value empty (no managed runtime). |
| IISSettings.IdentityType | The [identity type](https://docs.microsoft.com/en-us/iis/configuration/system.applicationhost/applicationpools/add/processmodel) . |
| IISSettings.ApplicationName | The name of the IIS application if applicable. |
| IISSettings.ApplicationPoolName | The name of application pool. |
| <a name="IISUser"></a> IISSettings.ApplicationPoolUser | The name of user to use as service identity. |
| <a name="IISPw"></a> IISSettings.ApplicationPoolPassword | The password of the specified application pool user. If no password is given and the IdentityType is set to 3, the script will prompt for the password during installation. |
| IISSettings.Bindings | List of bindings |
| IISSettings.Bindings.Protocol | The protocol contains *http* or *https* |
| IISSettings.Bindings.IPAddress | The IP address to use. Default is * for all IP addresses. |
| IISSettings.Bindings.Port | The port is an integer. The default port for *http* is 80 and for *https* 443. |
| IISSettings.Bindings.HostName | The hostname for the binding. Use * for all hostnames. |
| IISSettings.Bindings.CertificateHash | The thumbprint hash of the certificate you want to use. ([This is how you get the fingerprint.](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate)) |
---
### AppSettings:
| Name | Description |
| ---| ---|
| Server| Name or address including port of your database server|
| Initial Catalog| The name of your database|
| Persist Security Info| With `false` security relevant information is not returned (recommended) |
| User ID| The user of the database. The user must have authorizations on the database|
| Password| The password of the database user|
| MultipleActiveResultSets| Setting for multiple return by the server|
| TrustServerCertificate| Trust of the server certificate, ensures an encrypted connection|
| Connection Timeout| Request waiting time in seconds for server |
---
If all settings are corretly set, please start a new powershell console as administrator, change into the directory of the downloaded script, and run the following command:
```PowerShell
.\Install-SymbioWeb.ps1 -ParametersFile .\symbio-service-uniqueid.parameters.json
```

*`nice to know`*

*- if you use a domain user. You must write [server] \\\\\\\\ [user].*

*- You can omit the specification of the Files parameter by renaming symbio-service-uniqueid.parameters.json to parameter.json. The script detects the JSON itself, if they are in the same folder.*

Install the [.NET Core Windows Server Hosting Package](install-manual.html#NetCore) after Scripted Installation
