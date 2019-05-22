# Element information get

**api-version**: 1.0

Retrieves information for a specific element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/info
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| elementId | path | true | string | The ID of the element. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [ElementInfo[]](#elementinfo) | The list of element information. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the element information

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/info
```

#### Response (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "elementTypeName": "SubProcessDiagram",
            "entityIds": [
                "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5"
            ],
            "entityTypeName": "MTX_SUB_PROCESS",
            "facetTypeName": "Processes",
            "facetViewKey": "PersonalizedDiagram",
            "hasDiagram": true,
            "hasEditPermission": true,
            "id": "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "insertableDynamicTypes": {},
            "isCurrentCopyable": false,
            "isCurrentInsertable": true,
            "isCurrentMovable": true,
            "isCurrentRemovable": true,
            "isReadOnly": false,
            "isReadOnlyCollection": false,
            "name": "Idea/Innovation",
            "permissions": [
                "NewElement",
                "EditElement",
                "DeleteElement",
                "ShowElement",
                "ApproveElement",
                "OpenElement"
            ],
            "readOnlyCollectionContext": "None",
            "readOnlyContext": "None",
            "rootPath": [
                "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5"
            ],
            "shapeId": "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "typeColor": "#007ACC",
            "uid": "_f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5"
        }
    ]
}
```

## Definitions

### ElementInfo
{!developer/rest-api/reference/models/elementinfo.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
