# Views get

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
| values | [FacetView[]](#facetview) | The list of views. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the list of views of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views
```

#### Response (200 OK)
```json
{
    "count": 10,
    "values": [
        {
            "name": "detail",
            "displayName": "All information on processes",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements"
        },
        {
            "name": "detail",
            "displayName": "All information on processes",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements"
        },
        {
            "name": "diagram",
            "displayName": "Graphic",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements"
        },
        {
            "name": "diagram",
            "displayName": "Graphic",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements"
        },
        {
            "name": "diagram",
            "displayName": "Graphic",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements"
        },
        {
            "name": "documentContent",
            "displayName": "Document content",
            "isHierarchical": true,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/documentContent/elements"
        },
        {
            "name": "documentContent",
            "displayName": "Document content",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/documentContent/elements"
        },
        {
            "name": "list",
            "displayName": "List",
            "isHierarchical": false,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/list/elements"
        },
        {
            "name": "reporting",
            "displayName": "Report data",
            "isHierarchical": true,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/reporting/elements"
        },
        {
            "name": "tree",
            "displayName": "Architecture",
            "isHierarchical": true,
            "elements": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements"
        }
    ]
}
```

## Definitions

### FacetView
{!developer/rest-api/reference/models/facetview.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
