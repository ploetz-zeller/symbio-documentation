# Scripted Installation

## Requirement

- Powershell Version 5.0 or higher. Download [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395)
- Download the **Install.ps1** file from the [Operations Page](http://operations.symbioworld.com/).
- Download the **symbio-service-rendering.parameters.json** file from the [Operations Page](http://operations.symbioworld.com/).
- Open and edit the symbio-service-rendering.parameters.json file.

Replace the settings with your own values:
### Parameters:
| Name | Description  |
| ---|---------------------------------------|
| SourcePath | The download or local path of the installation package (zip file).  |
| <a name="TargetPath"></a>TargetPath | The local directory for the Service  |
| NetFrameworkPath | The download or local path of the NetFramework installation package (exe).  |
| ServiceSettinigs.ApplicationName | The name of your application which should be run as a Windows service, e.g. Service.exe |
| ServiceSettinigs.ServiceName | The name with which the service is registered |
| ServiceSettinigs.AppConfig | The XML node for the AppConfig. Adjust the target urls and the service name so that they are the same as your binding 
| ServiceSettinigs.Bindings | List of bindings |
| ServiceSettinigs.Bindings.Protocol | The HTTP protocol. Only *https* is supported |
| ServiceSettinigs.Bindings.Port | The port is an integer. The default port for *https* is 443 |
| ServiceSettinigs.Bindings.HostName | The hostname for the binding. |
| ServiceSettinigs.Bindings.CertificateHash | The thumbprint hash of the certificate you want to use. ([This is how you get the fingerprint.](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate)) |
| ServiceSettinigs.Bindings.HostUser | The hostuser for the binding. This can be a domain user (DOMAIN/User) or use 'everyone' for unknown users |

If all settings are corretly set, please start a new powershell console as administrator, change into the directory of the downloaded script, and run the following command:
```PowerShell
.\Install.ps1 -ParametersFile .\symbio-service-rendering.parameters.json
```

*`nice to know`*

*- You can omit the specification of the Files parameter by renaming symbio-service-rendering.parameters.json to parameter.json. The script detects the JSON itself, if they are in the same folder.*
