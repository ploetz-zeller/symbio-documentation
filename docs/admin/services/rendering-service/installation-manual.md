# Manual Installation

1. **Download the installation package and extract the contents to the desired location.**
   
   Please ensure that the (dedicated) service user account has sufficient rights in the target folder or the service won't start.

    You can download the package [here](https://symbioworld.com/download/symbio/symbio-service-rendering.zip)

2. **Reserve the URL(s) the service should listen on using netsh**, on a command line execute:
   ```
   netsh http add urlacl url=https://+:3334/ user=everyone
   netsh http add urlacl url=https://localhost:3334/ user=everyone
   ```

   The above example is the most simple way to reserve the default URL of the service.
   The generic version of the command looks like this:
   ```
   netsh http add urlacl url=[http-or-https]://[host-name-and-domain]:[port]/[possible-path/] user=[DOMAIN\username]
   ```
   
   ### HTTPS

   **Symbio will allow HTTPS only.**

   For reserving an HTTPS URL you need two things:
   - an SSL certificate
   - a binding of that certificate to a port

   #### SSL certificate thumbprint
   You need an SSL certificate for HTTPS bindings. Please, ask your system administrator for assistance. As soon as the certificate is available and installed on the service machine, you can retrieve its thumbprint following the description in this article: [How to: Retrieve the Thumbprint of a Certificate](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate) (with the intended purpose being "Server Authentication" here). You will need this thumbprint (without spaces) in the next step.

   #### SSL certificate port binding
   ```
   netsh http add sslcert hostnameport=[host-name-and-domain]:[port] certhash=[thumbprint] appid={BD856AF7-ACAA-4B81-B2F9-B19845E12AE5} certstorename=my
   ```

   The appid given above is unique and meant to identify the Symbio Rendering Service, regardless of where and how often it is installed.

   More details for binding HTTPS URLs can be found in this article: [How to: Configure a Port with an SSL Certificate](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate)

3. **Update the file Symbio.Rendering.exe.config**

   If you changed the endpoint at which the service should listen during URL reservation above,
   please also change the endpoint in the confguration file (setting "Uris") from *https://localhost:3334*
   to the one you selected.

   You should also decide the name under which the service should be installed in the service manager now.
   If you want to change the default name, please change it in the configuration file (setting "ServiceName")
   from *SymbioRenderingService* to the one you want to use.

4. **Install the rendering service in the service manager**, on a command line execute:
   ```
   installutil [/name=<service-name>] <assembly-path>
   ```

   Set < service-name > to the name you selected above, or ignore the whole option if you want to stay with the default name and didn't change it in the configuration file.

   Set < assembly-path > to the full path to Symbio.RenderingService.exe, including file name and extension.

   **You will need to enter user credentials for the user account which will run the service.**

   InstallUtil can usually be found here: C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe

   **The Rendering Service is a 64-bit application so you need to use the 64-bit InstallUtil with it!**

   ### Attention

   - If /name is provided it must also be set in the application config file!
   - If /name is provided it must also be used during de-installation!