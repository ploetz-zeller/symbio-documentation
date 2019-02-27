---
uid: creating-token-and-inform-external-systems
---
User can configure the **CreateTokenAndInformExternalSystem** converter step in the link converter file attached to the external system.

The converter step has following settings 
- AuthTokenOriginKey: The origin key of the auth token
- AutomationParent: The origin key of the automation task
- Role: Application role of the token
- ExternalSystemKey:  External system origin key that should be informed. Use [Id]
- TokenName: Name of token

Example:
```
<CustomOperation>
      <!--Sends an authTokenCreated event to x.Reach-->
      <Settings Implementation="CreateTokenAndInformExternalSystem">
        <Setting Name="AuthTokenOriginKey" Value="7C556DA0-18A8-425E-9FAE-AA11704A9B3A" />
        <Setting Name="AutomationParent" Value="771799E7-04F5-4532-B5FC-81375E994BB0" />
        <Setting Name="Role" Value="Administrator" />
        <Setting Name="ExternalSystemKey" Value="[Id]" />
        <Setting Name="TokenName" Value="ExternalSystemToken-[AT_ID]" />
      </Settings>
    </CustomOperation>
```

Upon execution of the converter step a cloud event will be sent to the external system:

````
{
	"cloudEventsVersion": "0.1",
	"contentType": "application/json",
	"data": {
		"authorizationToken": {
			"id": "7C556DA0-18A8-425E-9FAE-AA11704A9B3A",
			"type": "authToken",
			"attributes": {
				"id": {
					"127": "y0ag79uzmwbnt85cgg6yr8t2c0"
				},
				"roleAdministrator": {
					"127": true
				},
				"roleAnalyzer": {
					"127": true
				},
				"roleApprover": {
					"127": true
				},
				"roleArchitect": {
					"127": true
				},
				"roleEditor": {
					"127": true
				},
				"roleInactive": {
					"127": false
				},
				"roleViewer": {
					"127": true
				},
				"validFrom": {
					"127": "2018-08-10T00:00:00"
				},
				"validUntil": {
					"127": "2018-11-08T00:00:00"
				}
			}
		},
		"externalSystem": {
			"id": "15d2ccad-d919-4596-8d79-3d4d2347f725",
			"attributes": {
				"id": {
					"127": "ExternalSystem"
				}
			}
		},
		"storage": {
			"id": "e363e8a1-8932-41d6-a927-84656858e79a",
			"type": "storage",
			"attributes": {
				"id": {
					"127": "Storage"
				},
				"name": {
					"1031": "Storage",
					"1033": "Storage"
				}
			}
		}
	},
	"eventID": "t30uksxkh6n4zaew1fm8wmkus6",
	"eventTime": "2018-08-10T08:50:13.0959963Z",
	"eventType": "systemTokenCreated",
	"eventTypeVersion": "1807.1.0.2018-07-25T11:42:13.89004d2c250263b9f4aa0c2ca851a9705aafa032 (Updated on: 18/08/10 10:37:10)",
	"source": "https://symbio-dev/StorageCollection/Storage/_api/"
}
````