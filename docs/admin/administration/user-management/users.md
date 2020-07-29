# User Management

This chapter shows the administration of users and their assignment to individual user groups.
If these are to receive specific rights, please refer to [Permissions](../permissions/permissions.md).

## User

### Set up users

By clicking on New, please enter a name for each new user and confirm. 

![screen](../media/user-insert-panel.PNG)

In the Detail Content, add user's e-mail address and assign a password. 

You will also need to define the appropriate __Application roles__ for each user by specifying if the user acts as Viewer, Author or Approver etc. For this, please select __Change permissions__ in the Toolbar.

![screen](../media/Appl_roles.png)

You can assign a user to a number of user groups, if required.

In the case of an AD connection via SAML users are automatically created with Viewer rights by default if not changed.

### Consolidate users

Users can be consolidated if there are redundancies. 

To start consolidation, please select the target user and click the consolidate button of the toolbar.

![screen](../media/consolidate.png)

In the following dialogue please choose all source users you wish to consolidate with the target and click OK. You will be prompted with a confirmation dialog showing information about your selected elements before the actual consolidation will be performed. By clicking OK, the consolidation is executed, clicking on “Cancel” leads you back to the source selection dialog.

The process of consolidating users cannot be reversed.

## User groups

### Set up user groups

You set up user groups in the same way as you create users. Click the User groups tile.

After you have created the user group using the New option and have assigned a name to the group, you can select the users for this group in the Detail Content area. Click the hamburger icon on the Users screen to display a list with all users. Select the required users and click OK. 

![screen](../media/user-list.png)

SAML user groups additionally have Application Roles which sets the Application roles of their user/members if SAML group management is activated.

### Consolidate user groups

Users can be consolidated in the same way es users - via the consolidate button. 

In the dialog which then appears, please choose the elements you want to consolidate with the target element and click OK.

The process of consolidating user groups cannot be reversed.
