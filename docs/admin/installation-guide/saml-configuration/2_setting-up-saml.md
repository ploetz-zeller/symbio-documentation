---
uid: setting-up-saml
---
# Symbio SSO

## Setting Up SAML-based SSO

SAML has to be set up on the Identity Provider (IdP) and the Service Provider (SP), thereby creating the mutual trust relation.

### Basic requirements

The following basic requirements must be fullfilled to consider SAML-based SSO at all:

* SAML 2.0-compliant IdP with
  * SSO-REDIRECT endpoint
  * ability to POST to an ACS endpoint
  * SHA-256 signature support
  * IdP Metadata XML file
  * a trustworthy (in respect to your organization) certificate contained in the Metadata file
* Symbio installed on a HTTPS/SSL/TLS binding
* IdP and Symbio reachable by browsers in the company networking scenario

### Setting up the IdP

To set up the IdP you need to define Symbio as a relying party trust. The following information is essential for that:

* SP Entity ID: The unique ID/name of the SP
  * To be configured in newer Symbio versions - decide on an appropriate string beforehand, we suggest something like this: "urn:symbio.company.tld:an-additional-instance-id"
  * Predefined for older Symbio versions: "http://symbioworld.com/web"
* SSO-REDIRECT: Accept requests by Symbio at the SSO-REDIRECT endpoint
* ACS-POST: Send responses to the ACS endpoint of Symbio via POST
* Request Signing/Encryption: Symbio does not (normally) sign nor encrypt requests
* Response Signing/Encryption: Symbio expects responses to be signed

The URL of Symbio is most likely needed during IdP configuration. Sometimes the ACS endpoint URL is also needed. This can be derived from the Symbio URL:

* Symbio URL example: https://symbio.company.tld
* Corresponding ACS URL: https://symbio.company.tld/AuthServices/Acs

If Symbio is mapped to a path, the path needs to be included:

* Symbio URL example with path: https://portal.company.tld/symbio/production
* Corresponding ACS URL with path: https://portal.company.tld/symbio/production/AuthServices/Acs

Never include database collections nor databases in these URLs; the ACS endpoint is used by all databases and collections of a Symbio instance.

Attention: Symbio only supports SP-initiated authentication. Please bear this in mind when setting up your IdP.

#### Transmitted Claims

Symbio expects the following claims:

* UPN (upn: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn)
* Last Name (surname: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname)
* First Name (givenname: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname)
* E-Mail (emailaddress: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress)

For rights management group claims should also be transmitted:

* Group (group: http://schemas.xmlsoap.org/claims/Group)

If your system cannot provide these claims, please see "Custom Claims Mapping" below.

### Setting up Symbio as the SP

The most important part to set up Symbio as the SP is the Metadata XML file of the IdP. Normally all other information can be derived from this file:

* SP Entity ID: The unique ID/name of the SP (see above, "Setting up the IdP")
  * Newer versions of Symbio allow & require you to define it yourself
  * Older versions of Symbio have a predefined ID
* IdP Entity ID: The unique ID/name of the IdP (can normally be found near the top of the Metadata XML)
* IdP Metadata XML file: You can choose to provide it in several ways to Symbio:
  * Upload: The file will be stored locally and no network requests are required to retrieve its contents. If the certificate for signing responses changes on the IdP you need to update the upload in Symbio.
  * URL: The file will not be stored locally, it will be cached temporarily to reduce network traffic. Certificate changes on the IdP do not require updates on the Symbio side. The Symbio instance must be able to access the Metadata URL of the IdP.
* IdP SSO Service URL: The SSO-REDIRECT endpoint URL of the IdP (can normally be found near the bottom of the Metadata XML)

### Advanced Setup Topics

#### Explict SP Host URL

In some scenarios Symbio might be accessed via another URL than the one of the host Symbio is installed on (e.g. when accessed via a proxy server). In such a case the host URL of Symbio needs to be adjusted for the SAML authentication flow so the IdP can direct the browser back to an address it can access (the proxy instead of Symbio's host).

In such a case provide a corresponding "SP Host URL" in Symbio's SAML configuration (only available in newer versions of Symbio).

#### Request Signing

Symbio supports request signing but does not use it by default. To enable request signing you need to provide a certificate to Symbio via its SAML configuration. This certificate must provided as a file which fullfills the following requirements:

* Base64-encoded PFX file
* containing the private key
* without password protection

#### Custom Claims Mapping

Some IdPs cannot provide the claims Symbio expects. To mitigate you can provide a Claims Mapping XML file. Symbio comes with a sample XML file in the data directory which provides a mapping that can easily be used with Azure AD.

Please contact your sales or partner contact person to assist in setting up an individual claims mapping for your system.
