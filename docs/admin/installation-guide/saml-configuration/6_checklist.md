# Symbio SSO

## Checklist

The following checklist aids you in collecting all necessary data to get started with setting up SAML for Symbio.

### Is your Infrastructure Ready for Symbio SSO?

If you can answer every question with Yes, your infrastructure is Ready for Symbio SSO.

| Question                                           | Answer                 |
| -------------------------------------------------- | ---------------------- |
| Symbio and IdP both reachable by browser?          | &#9744; Yes &#9744; No |
| SAML 2.0-compliant IdP available?                  | &#9744; Yes &#9744; No |
| SSO HTTP-REDIRECT endpoint supported?              | &#9744; Yes &#9744; No |
| POST to ACS endpoint supported?                    | &#9744; Yes &#9744; No |
| SHA-256 signatures supported?                      | &#9744; Yes &#9744; No |
| IdP Metadata XML file available?                   | &#9744; Yes &#9744; No |
| Metadata contains trustworthy certificate?         | &#9744; Yes &#9744; No |
| (If on premise) Symbio installed on HTTPS binding? | &#9744; Yes &#9744; No |

Please provide the IdP Metadata XML file to Ploetz + Zeller GmbH to get your Cloud instance of Symbio configured for SSO.

#### Claims Details

| Additional Question                   | Answer (needed by P+Z for Cloud setups) |
| ------------------------------------- | --------------------------------------- |
| Claim Type users are identified by?   | (UPN preferred)                         |
| Claim Type used for group membership? | (Group preferred)                       |

If these answers diverge from the desired claim types, a custom claims mapping needs to be added.

### What is needed for Setting up your IdP?

The following data is most likely needed to setup your IdP:

| Element          | Value                                          |
| ---------------- | ---------------------------------------------- |
| Initiated By     | Service Provider (IdP-initiated not supported) |
| SP Entity ID     | http://symbioworld.com/web                     |
| SSO Service      | Expect HTTP-REDIRECT                           |
| AuthnRequest     | Expect Unsigned                                |
| ACS Type         | Set to HTTP-POST                               |
| Response         | Set to Signed                                  |
| SP URL           | Symbio Root URL (Cloud: provided by P+Z)       |
| ACS URL          | Symbio Root URL + "/AuthServices/Acs"          |
| Minimal Claims   | (see below)                                    |

#### Minimal Claims expected by Symbio

* UPN (upn: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn)
* Last Name (surname: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname)
* First Name (givenname: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname)
* E-Mail (emailaddress: http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress)
* Group (group: http://schemas.xmlsoap.org/claims/Group)

If your claims diverge from this list, please provide P+Z with a list of transmitted claims.