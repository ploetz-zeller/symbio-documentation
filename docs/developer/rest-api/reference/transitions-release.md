# Transitions release

**api-version**: 1.0

Retrieves transitions of a specific element which is in "Release" state. 

```
POST /{collectionId}/{storageId}/_api/release/{elementId}/transitions
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| elementId | path | true | string | The ID of the element. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [Transition[]](#transition) | The list of transitions. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/release/664fd624-d341-4521-b430-897bb16399f4/transitions
```

#### Response (200 OK)
```json
{
    "count": 1,
    "transitions": [
        {
            "transitionId": "ReleasedToRequestToExpire",
            "sourceState": "released",
            "targetState": "requestToExpire"
        }
    ]
}
```

## Definitions

### Transition
{!developer/rest-api/reference/models/transition.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
