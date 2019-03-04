# List

**api-version**: 1.0

Retrieves a specific related contexts.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/related/{relatedId}
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/related?$filter={filter}&$expandRelated={expand}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| elementId | path | true | string | The ID of the element. |
| relatedId | path | true | string | The name of the related context. |
| $filter | query | | string | |
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [Element[]](#element) | The list of related elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the *author* related context of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/related/author
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": {
        "author": [
            {
                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/ab01a052-80f2-4fbf-8e21-698cb7095b34/List"
            }
        ]
    }
}
```

### Get and expand the *author* related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/related/author?$expandRelated=author
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": {
        "author": [
            {
                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/ab01a052-80f2-4fbf-8e21-698cb7095b34/List",
                "related": {
                    "changedBy": [
                        {
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user",
                            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/a364f30b-a126-4a74-9e1a-1df87f2a6074/List"
                        }
                    ],
                    "createdBy": [
                        {
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user",
                            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/a364f30b-a126-4a74-9e1a-1df87f2a6074/List"
                        }
                    ]
                }
            }
        ]
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
