---
uid: attributesget
---
# Attributes

**api-version**: 1.0

Retrieves a specific attribute.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes/{attributeId}
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes?$filter={filter}&$select={select}
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
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the *name* attribute

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/attributes/name
```

#### Reponse (200 OK)
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

### Element
{!developer/rest-api/reference/models/element.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
