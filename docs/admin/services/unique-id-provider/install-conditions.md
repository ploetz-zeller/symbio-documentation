---
uid: uniqueid-install-conditions
---
# General conditions

There are the following requirements for the installation of the Unique ID provider service:
- [.NET Core Windows Server Hosting bundle](https://aka.ms/dotnetcore-2-windowshosting)
- symbio-service-uniqueid.zip
- The following operating systems are supported:
  - Windows 7 and newer
  - Windows Server 2008 R2 and newer
- SQL Server connection without using SQL Server alias. Currently SQL Server aliases are not supported.
    - Create a new Databse for the Service
- A dedicated user with read/write access to the [TargetPath](install-scripted.md#TargetPath) directory. 
  - Replace [IISSettings.ApplicationPoolUsers](install-scripted.md#IISUser) and [IISSettings.ApplicationPoolPassword](install-scripted.md#IISPw) with dedicated user.
