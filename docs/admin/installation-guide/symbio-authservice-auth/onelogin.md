# Configuring OneLogin for use with the Symbio AuthService

Please follow the instructions in [Configuring OneLogin for use with Symbio Apps](../symbio-apps-auth/onelogin.md) but adjust the _ACS (Consumer) URL_ as follows:

`https://auth.symbio.cloud/<customer>-saml/Acs`

Example: https://auth.symbio.cloud/symbio-saml/Acs

## Claims

The following claims are required and must be sent by the external IdP.

- email (contains the email address of the user)
- given_name (contains the given, e.g. first name of the user)
- family_name (contains the family, e.g. last name of the user)

If the external IdP uses different claim types, make sure to provide a set of claim types (names) that contain the required data. Deviating claim types can then be mapped to the corresponding required claim types in the Symbio AuthService.
