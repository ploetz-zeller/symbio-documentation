# Symbio SSO

## User & Rights Management Considerations

In Symbio users have attributes such as a name or an e-mail address. Additionally users can be members of user groups and have default permission sets assigned.

Based on the claims the Identity Provider (IdP) transmits to Symbio and the claims mapping defined in Symbio these attributes, memberships, and assignments can be updated and thereby ease user and rights management in Symbio.

The standard (see "Transmitted Claims") / custom (see "Custom Claims Mapping") claims mapping governs which information will be used by Symbio.

### Unique User ID

A user is identified by a unique key. Which claim will be used as this unique key can be configured. By default the User Principal Name (UPN) is used. Symbio does not analyze this ID, it just expects it to be unique and uses this ID for user lookup and identification.

### Attributes: Name, E-Mail Address, Telephone Number, etc.

There are many different claims which can be mapped to Symbio attributes. The default mappings are defined above (see "Transmitted Claims") and can be customized (see "Custom Claims Mapping").

All configured claims will automatically update associated user attributes upon each user login. That way Symbio's user data stays automatically synchronized to the IdP's userbase which remains the single source of truth.

### Group Memberships and Permissions

In Symbio permissions are managed in a three-fold way:

* Role-based permissions (Viewer, Editor, Admin, etc.)
* User default permissions by assigment of a named permission set
* User Group-based permissions inherited through group memberships

If no group-based permissions apply, user default permissions are used.
If no user default permissions are set, role-based permissions are used.

#### SAML Group Management Activated

You can configure Symbio to use SAML group claims (see "Transmitted Claims") to manage those permissions for you.

During each user login group claims are evaluated if "SAML group managment" has been activated. In this case the following steps are taken:

1. The SAML user is removed from all SAML user groups
2. The SAML user's default permissions are removed
3. The SAML user is added to each SAML user group which exists in Symbio and which the received group claims contain - the matching is done based on the user group name/group claim value
4. The SAML user is assigned each permission set which exists in Symbio and which the received group claims contain - the matching is done based on the permission set name/group claim value
5. A user role is assigned:
   * The SAML user is a member of at least one SAML user group: The highest role from all SAML user groups he is a member of
   * The SAML user is NOT a member of any SAML user group: The standard user role configured in the SAML configuration

#### SAML Group Management Not Activated

If "SAML group management" has not been activated, you need to assign all permissions manually.

There exists one exception (Symbio 1808 and later):

The first time a user logs into a database using SAML, i.e. when a user is created in the database due to a SAML login, they get a role assigned based on the Standard Role configured for the current authentication provider.

Subsequent logins will not reapply the Standard Role so that manual changes to a user's role won't get overwritten.
