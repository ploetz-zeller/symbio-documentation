---
uid: views
---
# Views

**api-version**: 1.0

Retrieves the list of views.

```
POST  /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [View[]](#view) | The list of views. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the list of views of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views
```

#### Reponse (200 OK)
```json
{
    "count": 3,
    "values": [
        {
            "name": "detail",
            "displayName": "All information on processes",
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements"
        },
        {
            "name": "list",
            "displayName": "List",
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/list/elements"
        },
        {
            "name": "tree",
            "displayName": "Architecture",
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements"
        }
    ]
}
```

## Definitions

### View
{!developer/rest-api/reference/models/view.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
