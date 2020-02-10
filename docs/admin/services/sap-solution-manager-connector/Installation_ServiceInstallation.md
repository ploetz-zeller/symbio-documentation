

# SAP Solution Manager Interface Set-up Documentation

This document contains information on how to set-up **SAP Solution Manager** service and configure Symbio so it can use it.

## 1. Service set-up   


1. Create a SQL Server database which will be used by the service as a configStore.
2. In that database create a table dbo.settings with columns: Key(nvarchar(1024), null) and Value(nvarchar(max), null).
3. In appsettings.json set the following configuration:
```json
{
    "ConfigStoreConnection": "Server=[SERVERNAME];Database=[DATABASENAME];Trusted_Connection=True;",
    "ConfigStoreTableName": "settings",
    "Serilog": {
        "MinimumLevel": "Verbose",
        "WriteTo": [
            {
                "Name": "File",
                "Args": {
                  "path": "Logs\\log.txt",
                  "rollingInterval": "Day"
                }
            }]
    },
    "AllowedHosts": "*"
}
```
4. (Optional) Set sensitive data in user secrets. (in development "ConfigStoreConnection").
5. (Optional) Change Serilog settings in appsetting.json if needed.


## 2. Setting SAP Solution Manager run on premise 
Step two is needed only if the SAP Solution Manager micro-service is installed on premise.
Here it will be explained how to set up the SAP Solution Manager micro-service on IIS to run on an on premise solution.
Prerequisites for setting SAP Solution Manager interface on premise:

1. Running Symbio instance(1904 or higher)
2. Valid relational database connection string for a database the micro-service can use. An empty database has to be created manually.
3. Accessible SAP Solution Manager instance ***https://{ip}:{port}/sap/opu/odata/sap/processmanagement/*** with provided valid certificate
4. Provided valid certificate for SAP Solution Manager interface. Who is responsible for this?
5. For the machine where the micro-service will run we need .Net Core Hosting bundle (for .Net core 3.1 applications) installed
6. Powershell version 5 or higher (so we can run the install script)

### 2.1 Get zip file of a micro-service build

You can get it on the Symbio world FTP server.


### 2.2 Configure the parameters json to create application site

Download the parameters json from here:
http://operations.symbioworld.com/
Parameters.json will be used by the powershell script called Install.ps1. 

Open the parameters.json

The following parameters should be changed:
```json
"SourcePath": - path to your zip file of the micro-service 
"BaseTargetPath": - path to where the script will be unzipped
"InstanceName" : - should be Symbio-Service-SolMan
"IISSettings":
        "SiteName": - should be Symbio-Service-SolMan
        "ApplicationPoolName": - should be Symbio-Service-SolMan
        "ApplicationPoolUser": - should be the current user example (INT\username)
        "ApplicationPoolPassword": - should be the user password
        "Bindings": 
            "Protocol": "https"
            "Port": - use available port
            "HostName": - give it a wanted hostname
            "CertificateHash": - provide the certificate hash you want to use ( found in the iis -Server Certificates. It should be in local machine , personal or trusted root )
            "CertificateCN" : - provide name of certificate (found in the iis -Server Certificates)
            
"AppSettings":-
    "ConfigStoreConnection": - give right connection string to the database( you have to create the database yourself)
```
        
### 2.3 Run the script

Turn on Powershell.
Navigate to the folder where you script is.
Run the command :
Set-ExecutionPolicy
Provide the parameter called Execution policy : unrestricted.

Then run the following line:
 ./Install.ps1 -ParametersFile symbio-service-solman.parameters.json
 
 This will create the application pool and site for the micro-service.
 
 To check if the site is working your can call this request from your browser
 ***https://{domain}:{port}/api/values***.
 it should return a simple response just to make sure its working.
 
### 2.4 Set the SAP Solution Manager certificate to be trusted
 The client should provide te valid certificates for the SAP Solution Manager micro-service and for the SAP Solution Manager API.
 
 If for some reason the client cant provide the certificates, in order for the micro-service to work he has to communicate with SAP Solution Manager API.
 SAP Solution Manager API could have a certificate that is not trusted so you  have to export it to your computer and then put it into the MMC -> Certificates-> Trusted Root Certification Authorities. This way the connection will be safe.



