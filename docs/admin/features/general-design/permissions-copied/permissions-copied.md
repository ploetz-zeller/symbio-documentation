# Permissions get copied from comparable user instead of recalculated

This feature aims to accelerate the assignment of permissions to users for performance reasons.

When creating a new user, the system automatically checks if a user with the same permission basis (roles, permission sets etc.) already exists. If so, the permissions are copied, otherwise a new recalculation of permissions is triggered. 

The Facet permission feature and the Architectural Permissions feature remain unaffected and may be activated separately if required.