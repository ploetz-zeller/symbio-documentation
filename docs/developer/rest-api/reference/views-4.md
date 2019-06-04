# Views get

**api-version**: 4.0

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
  "count": 4,
  "values": [
    {
      "name": "detail",
      "displayNames": {
        "1031": "Alle Informationen zu Prozessen",
        "1033": "All information on processes",
        "3082": "Toda la información sobre los procesos"
      },
      "isHierarchical": false,
      "elements": "https://demo.symbioworld.com/Test/TestTHa/_api/rest/facets/processes/views/detail/elements"
    },
    {
      "name": "list",
      "displayNames": {
        "1031": "Liste",
        "1033": "List",
        "3082": "Lista"
      },
      "isHierarchical": false,
      "elements": "https://demo.symbioworld.com/Test/TestTHa/_api/rest/facets/processes/views/list/elements"
    },
    {
      "name": "reporting",
      "displayNames": {
        "1031": "Report-Daten",
        "1033": "Report data",
        "3082": "Datos del informe"
      },
      "isHierarchical": true,
      "elements": "https://demo.symbioworld.com/Test/TestTHa/_api/rest/facets/processes/views/reporting/elements"
    },
    {
      "name": "tree",
      "displayNames": {
        "1031": "Architektur",
        "1033": "Architecture",
        "3082": "Arquitectura"
      },
      "isHierarchical": true,
      "elements": "https://demo.symbioworld.com/Test/TestTHa/_api/rest/facets/processes/views/tree/elements"
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
