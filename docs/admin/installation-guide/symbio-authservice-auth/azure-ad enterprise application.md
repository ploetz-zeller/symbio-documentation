# Configuring Azure Enterprise Application (Single Sign-On) for use with the Symbio AuthService

Before you start align with the Symbioworld Team to provide you with the correct Assertion Consumer Service URL.

Please follow the instructions in [Worked Example: Symbio & Azure AD](../5_example-aad.md) but adjust the Assertion Consumer Service URL as follows:

`https://auth.symbio.cloud/<customer>-saml/Acs`

Example: https://auth.symbio.cloud/symbio-saml/Acs

## Claims

The following claims are required and must be sent by the Azure Enterprise Application.

- email (contains the email address of the user)
- given_name (contains the given, e.g. first name of the user)
- family_name (contains the family, e.g. last name of the user)

If the Azure Enterprise Application uses different claim types, make sure to provide a set of claim types (names) that contain the required data. Deviating claim types can then be mapped to the corresponding required claim types in the Symbio AuthService.

After the Setup is done send the Metadata Url or File to [Symbioworld Support](support@symbioworld.com) for further configuration on their side. 