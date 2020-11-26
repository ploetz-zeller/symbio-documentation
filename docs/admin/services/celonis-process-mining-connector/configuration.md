# Celonis Process Mining Connector Configuration

## Configuration
### Add the External System type to the Extended configuration on the system administration

1. Log on to the **/_sysadmin/_admin** section of Symbio (Requires System Administration access)
1. Switch to "Editor" mode
1. Go to the Admin area ![admin](media/admin.png)
1. Go to the "Extended configuration" ![extended configuration](media/extendedcfg.png)
1. Select "New" and add a type for an external system with a preferred name (e.g. Celonis Process Mining Connector)
1. Set the following attributes
   1. **Name:** (Preferred Name, e.g. Celonis Process Mining Connector)
   1. **Description:** This service is used to export Symbio processes to Celonis and/or vice versa
1. Upload the SYEX file under the settings "upload" group with the Title: "Celonis"
1. Activate the external configuration ![activate](media/addsyex3.png)
1. Apply changes ![Apply changes](media/apply.png)

### Add a configured external system linked to the active service
1. Select "External systems" on the main navigation bar
1. Add a new external system with Type of "CelonisProcessMiningConnector
   1. Name the External System "Celonis Process Mining Connector"
1. Add the URL data for the instance of the micro-service ![settings](media/celonis-synch-settings.png)

### Connect the external system on the storage
*Note: multiple storages can be connected to one instance of the service*
1. Select "Home" on the main navigation bar
1. Select a Storage Collection or create a new one
1. Select "Storages" on the main navigation menu
1. Choose an existing storage or create a new one
1. Under the external systems group, select the configured external system under the "Celonis Synchronization Service" drop down items ![choose external system](media/storage-external-systems-select-celonis.png)
1. Note at this point that you can select multiple different mining services for one storage if you want to

### Setting an API Key
1. Select "Home" on the main navigation bar
1. Select the storage you activated the Celonis Process Mining Connector for
1. Select the user flyout in the upper right corner of your view
1. In the flyout select the Tab "Settings"
1. On the bottom of the flyout, enter a valid Celonis API Key in the given field (1). For further information on how to generate a Celonis API Key, please visit https://(YourCelonisTeamDomain)/help/display/CIBC/User+Profile
![enter celonis api key](media/celonis-connector-token-flyout.png)

### Result after adding the external system
- Adding the external system to your repository will result in the following
    - All the required configuration will be added to Symbio
        - Possibility to add an API Key in the user flyout
        - Possibility to add an API Key in the "User" facet in the admin area
        - Two new services for pushing and/or pulling processes from Symbio to Celonis and vice versa
