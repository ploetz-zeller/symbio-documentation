# Permission sets

**api-version**: 1.0

Get the permission set data

```
GET  /{collectionId}/{storageId}/_api/rest/permissions/permissionsets/{Id}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| Id | path | true | string | The ID of the permission set |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [PermissionSetsPermission](#permissionsetspermission) | The permission sets permission. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message. |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the list of facets

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/permissions/permissionsets/7dd2a8fd-e262-494b-86b4-54ed74681d21
```

#### Response (200 OK)
```json
{
    "id": "7dd2a8fd-e262-494b-86b4-54ed74681d21",
    "users": [],
    "userGroups": [
        "1fe01960-8f0c-4423-928a-30782efd083d",
        "34b87d93-083a-48d0-8891-920ca6e51a3a"
    ]
}
```

## Definitions

### PermissionSetsPermission
{!developer/rest-api/reference/models/permissionsetspermission.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
