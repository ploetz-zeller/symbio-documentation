# Attributes get

**api-version**: 1.0

Retrieves a specific attribute.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes/{attributeId}
```

With optional parameters

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes?$filter={filter}&$select={select}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| elementId | path | true | string | The ID of the element. |
| attributeId | path | true | string | The name of the attribute. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [Attribute[]](#attribute) | The list of attributes. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the *name* attribute

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/attributes/name
```

#### Response (200 OK)
```json
{
    "count": 1,
    "values": {
        "name": {
            "1031": "Ideen/Innovationen",
            "1033": "Idea/Innovation"
        }
    }
}
```

## Definitions

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
