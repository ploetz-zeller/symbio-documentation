### Activating the Feature "Facet Permissions"

__You need to be an Administrator to activate this feature.__

* Go to the Admin area in Symbio and click on "Features":
![](media/activating-feature-facet-permissions-1.png)

* Select "Architectural Permissions" and change "Activation" to "Activated":
![](media/activating-feature-facet-permissions-2.png)

_Please note the consequences of activating this feature; read the explanation under "Activation" carefully._

### Changing permissions in Facet administration

* Go to the Admin are in Symbio and click on "Facets":
![](media/activating-feature-facet-permissions-3.png)

* Select facet to change permissions for and open Permissions menu from the toolbar
![](media/activating-feature-facet-permissions-4.png)

_Please note that Permissions menu in the toolbar was deactivated when Feature "Facet permission" is not active._

After selecting the Permissions menu item, new Permissions dialog will be opened. Permission dialog allows following options for defining permissions.

![](media/activating-feature-facet-permissions-5.png)
* Name (shows name of the selected item for which permissions are defined)
* Permitted groups (define what groups will be configured for selected item permissions, the selected item will be showed if user group have at least show permission)
* Inherit permissions ( does not affect permissions for facets)
* Permission mode
* Exclude other users (only users of selected user groups will have access to the selected item)
* Permissions of other users unchanged (users that are not part of the selected user groups are unaffected by permissions defined here)
* None (default permissions of user are used)

### Examples:

Only users from user group OrganizationAccess can access and edit elements from organization facet.

* Selected item: facet Organization
* Permission group: OrganizationAccess with permission set that have Show, Open, New and Delete permissions
* Inherit permissions: not important
* Permission mode: Exclude other users

_In this example only users that are part of user group OrganizationAccess can access menu item Organization and its sub-items. Also for this users organizations are visible and editable from the other parts of Symbio such as process diagrams. Other users that are not part of this user group will have no access to Organization facet._

Only users from user group OrganizationNoAccess can not access see or edit elements from organization facet.

* Selected item: facet Organization
* Permission group: OrganizationNoAccess with permission set that doesn't have any Delete permissions
* Inherit permissions: not important
* Permission mode: Permissions of other users unchanged

_In this example only users that are part of user group OrganizationNoAccess cannot see Organizations and its sub-items. Also for this users organizations are frozen from other parts of Symbio where Organizations are used. For other users that are not part of this user group facet Organization will work indecently of these permission settings._

