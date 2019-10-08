# Symbio SSO

## Worked Example: Symbio & AD FS

The Microsoft ActiveDirectory Federation Services provide a SAML 2.0 Identity Provider (IdP) implementation which is backed by a company domain's Active Directory. The following example describes setting up Symbio as a Service Provider (SP) in and for AD FS.

AD FS and IdP will be used interchangeably, the same holds true for Symbio and SP.

### Preparation of Active Directory

With respect to "User & Rights Management Considerations" start by creating appropriate UNIVERSAL (or at least global) user groups in ActiveDirectory (AD). AD FS will not transmit AD local user groups as group claims. Depending on your requirements you may have different user groups to create. The following is just an example.

* SymbioViewers will be able to browse the Symbio database
* SymbioAuthors will be able to edit parts of the Symbio database
* SymbioApprovers will be allowed to approve elements in the release cycle
* SymbioAnalysts will be able to run analysis extensions in the Symbio database
* SymbioArchitects will be able to manage the architecture of elements in the Symbio database
* SymbioAdmins will be able to administer the Symbio database (e.g. setting up user groups and permission sets)
* SymbioViewers_HR will be able to browse HR processes
* SymbioAuthors_HR will be able to edit HR processes
* SymbioApprovers_HR will be able to approve HR processes
* SymbioArchitects_HR will be able to manage HR architecture tasks

Next assign users to these user groups.

### Configuration of Symbio in AD FS

Before actually creating Symbio as a relying parts trust in AD FS, decide which EntityID you will give to Symbio and under which URL Symbio will be available. For this example we use the following values:

* Symbio EntityID: urn:symbio.example.com:adfs-example
* Symbio URL: https://processes.example.com/symbio-test/

In this case Symbio is available via a virtual subdirectory "/symbio-test/" and not directly on the subdomain root level.

#### Configure Relying Party Trust

Open the AD FS Management App and right-click on "AD FS/Trust Relationships/Relying Party Trusts", select "Add Relying Party Trust...", choose "Enter data about the relying party manually":

* Display name: Symbio Test
* Choose AD FS profile (not 1.0 nor 1.1)
* Don't configure a certificate
* Enable support for the SAML 2.0 WebSSO protocol
* Relying party SAML 2.0 SSO service URL: https://processes.example.com/symbio-test/
* Relying party trust identifier: urn:symbio.example.com:adfs-example
* Don't configure multi-factor authentication settings
* Permit all users to access this relying party

Make sure that the configured Endpoints are POST and that Advanced is set to SHA-256 secure hash algorithm.

#### Configure Claim Rules

Add the following claim rules:

1. Group Membership:
   * Send Claims Using a Custom Rule
   * Claim rule name: Group Membership
   * Custom rule:
     ```
     c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/windowsaccountname", Issuer == "AD AUTHORITY"]
     => add(store = "Active Directory", types = ("http://schemas.xmlsoap.org/claims/Group"), query = ";tokenGroups;{0}", param = c.Value);
     ```
2. Group Filter:
   * Send Claims Using a Custom Rule
   * Claim rule name: Group Filter
   * Custom rule:
     ```
     c:[Type == "http://schemas.xmlsoap.org/claims/Group", Value =~ "(?i)symbio"]
     => issue(claim = c);
     ```
3. Basic Attributes:
   * Send LDAP Attributes as Claims
   * Claim rule name: Basic Attributes
   * Attribute Store: Active Directory
   * User-Principal-Name &rarr; UPN
   * Surname &rarr; Surname
   * Given-Name &rarr; Given Name
   * E-Mail-Addresses &rarr; E-Mail-Address

### Configuration of AD FS in Symbio

Download the Metadata XML file from your AD FS. If your AD FS resides on https://fs.example.com then the metadata should be available at https://fs.example.com/FederationMetadata/2007-06/FederationMetadata.xml

The medatata file is a text file containing XML, you can read it using Notepad/Editor.

Usually it starts with the <EntityDescriptor> tag which has an "entityID" attribute whose value is the IdP EntityID we need to configure Symbio.

Near the end you will find the <SingleSignOnService> elements, look for the one with Binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-Redirect", its "Location" attribute value will be needed to configure Symbio.

Here are the values from the example metadata XML file:

* entityID: http://cadc05.example.com/adfs/services/trust
* Location: https://fs.example.com/adfs/ls/

#### Setting up a new SAML Authentication Provider in Symbio

Login as an administrator to the database or collection for which you want to activate SAML login. For this example we will set up SAML login for database "GreenField" in collection "Testing", the corresponding URL is https://processes.example.com/symbio-test/Testing/GreenField/editor/1033/

Switch to the Admin section and there to Authentication Providers. Make sure that the root node is set to "Use local" and then add a new SAML Authentication Provider with ID "ADFS". Select it and adjust its details:

* Translate (if you wish) - the ID stays "ADFS"
  * English: SSO Login
  * German: SSO Anmeldung
* Standard role: Viewer
* Group management: Yes
* Symbio EntityID: urn:symbio.example.com:adfs-example
* Symbio Host URL: https://processes.example.com/symbio-test/
* IdP EntityID: http://cadc05.example.com/adfs/services/trust
* IdP Metadata: (upload the XML file or link to it, see below)
* IdP SSO service URL: https://fs.example.com/adfs/ls/
* Enabled: Yes
* Visible: Yes

__Hint__

If you like to hide a specific login, e.g. for external non-AD users, by switching "Visible" from Yes to No, you can still reach the site by using the auth provider login explicitely. 
Example: https://processes.example.com/Collection/Storage/viewer/1033/Auth/Custom/SamlLegacy
where "SamlLegacy" is your SamlAuthProviderId in Symbio.

##### Symbio on Premise

If your Symbio web server can reach your AD FS server, consider adding the Metadata XML file as a URL (see above) instead of downloading it from AD FS and then uploading it to Symbio. That way changes to the metadata (e.g. a new certficate) don't require manual updates to Symbio.

##### Symbio in Cloud

Don't add the Metadata XML file as an URL. The cloud server will most likely have no access to the AD FS server which runs on your internal network; Symbio won't be able to access the metadata and therefore will fail on every SAML login attempt.

#### Configure SAML User Groups and Permission Sets

The new provider is now live and usable. Currently all new users logging in via SAML are made Viewers. We need to set up user groups and permission sets for details rights management:

1. Switch to the Admin area of your database/collection
2. Select Permission Sets and create the following sets:
   * SymbioViewers: ShowElement, OpenElement
   * SymbioAuthors: ShowElement, OpenElement, EditElement, NewElement, DeleteElement
   * SymbioApprovers: ShowElement, OpenElement, ApproveElement
   * SymbioViewers_HR: ShowElement, OpenElement
   * SymbioAuthors_HR: ShowElement, OpenElement, EditElement, NewElement, DeleteElement
   * SymbioApprovers_HR: ShowElement, OpenElement, ApproveElement
3. Switch back to the Admin area
4. Select User Groups, create the following SAML user groups, and assign them the listed permission sets / application roles :
   * SymbioViewers: SymbioViewers / Viewer
   * SymbioAuthors: SymbioAuthors / Author
   * SymbioApprovers: SymbioApprovers / Approver
   * SymbioAnalysts: SymbioAuthors / Analyst
   * SymbioArchitects: SymbioAuthors, SymbioApprovers / Architect
   * SymbioAdmins: SymbioAuthors, SymbioApprovers, SymbioApprovers_HR / Administrator
   * SymbioViewers_HR: SymbioViewers_HR / Viewer
   * SymbioAuthors_HR: SymbioAuthors_HR / Author
   * SymbioApprovers_HR: SymbioApprovers_HR / Approver
   * SymbioArchitects_H: SymbioAuthors_HR, SymbioApprovers_HR / Approver

Finally, you can set up permissions for your processes and repositories.

Now a user logging in via SAML will receive all rights based on his AD group membership. Examples:

* A user not member of any Symbio* user group will be assigned no permission sets, no user groups, and the default role of Viewer
* A user who is a member of SymbioAdmins and SymbioAuthors will get the following assignments:
  * SAML user groups: SymbioAuthors, SymbioAdmins
  * Permission sets: SymbioAuthors, SymbioApprovers, SymbioApprovers_HR
  * Role: Administrator
