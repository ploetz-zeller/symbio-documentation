# Symbio SSO

___Azure AD Premium is required___

## Worked Example: Symbio & Azure AD

The Microsoft Azure Active Directory provides a SAML 2.0 Identity Provider (IdP) implementation, too, though it does not provide group claims of any kind (see "User & Rights Management Considerations"). The following example describes setting up Symbio as a Service Provider (SP) in and for Azure AD.

Azure AD and IdP will be used interchangeably, the same holds true for Symbio and SP.

### Configuration of Symbio in Azure AD

Before actually configuring Symbio in Azure AD, decide which EntityID you will give to Symbio and under which URL Symbio will be available. For this example we use the following values:

* Symbio EntityID: urn:symbio.example.com:adfs-example
* Symbio URL: https://processes.example.com/

Append "AuthServices/Acs" to get the ACS URL of your Symbio instance.

#### Creating a new Application and Defining Claims

In your Azure Portal select Azure Active Directory / Enterprise applications - All applications:

* Click "+ New application"
* Choose "Non-Gallery Application"
* Choose "Manual Provisioning"
* Choose "SAML-based Sign-on"
* Enter Identifier (Entity ID): urn:symbio.example.com:adfs-example
* Enter Reply URL (Assertion Consumer Service URL): https://processes.example.com/AuthServices/Acs
* Select User Identifier: user.userprincipalname
* View and edit all other user attributes:
  * givenname &rarr; user.givename &rarr; http://schemas.xmlsoap.org/ws/2005/05/identity/claims
  * surname &rarr; user.surname &rarr; http://schemas.xmlsoap.org/ws/2005/05/identity/claims
  * emailaddress &rarr; user.mail &rarr; http://schemas.xmlsoap.org/ws/2005/05/identity/claims
* Save changes
* Download the Metadata XML file

### Configuration of AD FS in Symbio

The downloaded medatata file is a text file containing XML, you can read it using Notepad/Editor.

Usually it starts with the <EntityDescriptor> tag which has an "entityID" attribute whose value is the IdP EntityID we need to configure Symbio.

Near the end you will find the <SingleSignOnService> elements, look for the one with Binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect", its "Location" attribute value will be needed to configure Symbio.

Here are the values from the example metadata XML file:

entityID: https://sts.windows.net/0ee05e8d-dd1c-4065-a51c-840902926d66/
Location: https://login.microsoftonline.com/0ee05e8d-dd1c-4065-a51c-840902926d66/saml2

#### Setting up a new SAML Authentication Provider in Symbio

Login as an administrator to the database or collection for which you want to activate SAML login. For this example we will set up SAML login for database "GreenField" in collection "Testing", the corresponding URL is https://processes.example.com/Testing/GreenField/editor/1033/

Switch to the Admin section and there to Authentication Providers. Make sure that the root node is set to "Use local" and then add a new SAML Authentication Provider with ID "AAD". Select it and adjust its details:

* Translate (if you wish) - the ID stays "AAD"
  * English: Azure Login
  * German: Azure Anmeldung
* Standard role: Viewer
* Group management: No
* Symbio EntityID: urn:symbio.example.com:adfs-example
* Symbio Host URL: https://processes.example.com
* IdP EntityID: https://sts.windows.net/0ee05e8d-dd1c-4065-a51c-840902926d66/
* IdP Metadata: (upload the XML file or link to it, see below)
* IdP SSO service URL: https://login.microsoftonline.com/0ee05e8d-dd1c-4065-a51c-840902926d66/saml2
* Optional claim mapping: data > sso - azuread-samlclaimsmapping.xml
* Enabled: Yes
* Visible: Yes

##### Symbio in Cloud

If your Symbio web server can reach the Azure AD servers, consider adding the Metadata XML file as a URL (see above) instead of downloading it from Azure AD and then uploading it to Symbio. That way changes to the metadata (e.g. a new certficate) don't require manual updates to Symbio.

##### Symbio on Premise

Don't add the Metadata XML file as a URL. The Intranet server will most likely have no access to Azure AD servers on the Internet; Symbio won't be able to access the metadata and therefore will fail on every SAML login attempt.

#### Configure User Groups and Permission Sets

The new provider is now live and usable. All users logging in via SAML are made Viewers. As Azure AD does not transmit group claims you need to manage user group assignments manually.

Create user groups and permission sets as needed.

After a user has logged in for the first time you can access his data and change is application role, his default permission sets, and his user group memberships (don't use SAML user groups). As long as SAML group management is deactivated these values won't be changed automatically.
