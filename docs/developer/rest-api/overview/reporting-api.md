# Reporting API

Use these APIs to get variants and version of Symbio elements.

You can access the Swagger definition of these APIs using this URL: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Reporting%20Api%20(Version%201) - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance to get the latest definition applicable to your instance.

## Scenarios

- Use the **GET** `{storagecollection}/{tenant}/_api/v1/reporting` to page through all elements of a facet: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Reporting%20Api%20(Version%201)/ReportingV1_Get
  
  The parameters `facet` and `page` be given. `pageSize` is optional and must be in the range [1..1000], 100 being the default.

- Use the **GET** `{storagecollection}/{tenant}/_api/v1/reporting/{id}` to get one specific element (and its versions and variants): https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Reporting%20Api%20(Version%201)/ReportingV1_GetById
  
  No additional parameters are required/available.