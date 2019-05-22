# Elements delete

**api-version**: 2.0

Delete a specific element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/delete
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
| values | [OperationResult](#operationresult) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresulttype) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError[]](#opertionerror) | The list of errors. |

## Examples

### Delete a specific element from the *detail* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2d60031c-e501-47dc-9b50-76ef5f433878/delete
```

#### Response (200 OK)
```json
{
    "message": "Element has been deleted.",
    "output": "Volatile",
    "type": "Success"
}
```

## Definitions

### Element
{!developer/rest-api/reference/models/element.md!}

### OperationResult
{!developer/rest-api/reference/models/operationresult.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
