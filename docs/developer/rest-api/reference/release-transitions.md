---
uid: transitions
---
# Change state

**api-version**: 1.0

Retrieves transitions of a specific element.

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
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/release/664fd624-d341-4521-b430-897bb16399f4/transitions
```

#### Reponse (200 OK)
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
[!include[](models\transition.md)]

### OperationResultType 
[!include[](models\operationresulttype.md)]

### Error
[!include[](models\error.md)]
