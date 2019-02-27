# De-Installation

## Manual De-Installation

1. **Remove the service from the service manager**, on a command line execute:
   ```
   installutil /u [/name=<service-name>] <assembly-path>
   ```
   InstallUtil can usually be found here: C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe  
   The Rendering Service is a **64-bit application** so you need to use the 64-bit InstallUtil with it!

2. **Remove the URL reservation**, on a command line execute;
   ```
   netsh http delete urlacl url=https://+:3334/
   netsh http delete urlacl url=https://localhost:3334/
   ```

   (assuming you used the default reservation as described above)

   ### HTTPS

   Delete your SSL certificate port binding:
   ```
   netsh http delete sslcert hostnameport=[host-name-and-domain]:[port]
   ```

3. **Delete the folder containing the service**

    This is only possible if Service has been correctly stopped in above's steps.