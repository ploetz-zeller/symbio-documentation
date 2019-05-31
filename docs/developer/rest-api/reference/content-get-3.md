# Content - Get

**api-version**: 3.0

Retrieves the content of an element.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/content
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
| elements | [Element[]](#element) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the content of an element

#### Request

```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/1a526d30-f0c4-11df-4e21-001c25729284/content
```

#### Reponse (200 OK)
```json
{
    "count": 3,
    "elements": [
        {
            "properties": {
                "predecessors": [],
                "shapeId": "ea887eeb-060e-4b93-b1e9-35404109d3d5"
            },
            "id": "b61be5b7-7deb-4626-9158-b213fb0b8bd9",
            "creationId": "b61be5b7-7deb-4626-9158-b213fb0b8bd9",
            "type": "evStart",
            "attributes": {
                "name": {
                    "1033": "Start"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "a7bbe7cb-c8a1-412c-822c-770ce4854fb7"
                        },
                        "id": "a96e4089-bec7-4b8a-b5d0-556cfaefd1bf",
                        "creationId": "a96e4089-bec7-4b8a-b5d0-556cfaefd1bf",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/a96e4089-bec7-4b8a-b5d0-556cfaefd1bf"
                    }
                ],
                "shapeId": "30f7e585-77a7-49b4-a6ed-663c39b3e75d"
            },
            "id": "80921c19-7c72-4470-a621-8f369bd459c3",
            "creationId": "80921c19-7c72-4470-a621-8f369bd459c3",
            "type": "evEnd",
            "attributes": {
                "name": {
                    "1033": "End"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "ea887eeb-060e-4b93-b1e9-35404109d3d5"
                        },
                        "id": "b61be5b7-7deb-4626-9158-b213fb0b8bd9",
                        "creationId": "b61be5b7-7deb-4626-9158-b213fb0b8bd9",
                        "type": "evStart",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/b61be5b7-7deb-4626-9158-b213fb0b8bd9"
                    }
                ],
                "shapeId": "a7bbe7cb-c8a1-412c-822c-770ce4854fb7"
            },
            "id": "a96e4089-bec7-4b8a-b5d0-556cfaefd1bf",
            "creationId": "a96e4089-bec7-4b8a-b5d0-556cfaefd1bf",
            "type": "task",
            "attributes": {
                "name": {
                    "1033": "Task"
                }
            }
        }
    ]
}
```

## Definitions

### Element
{!developer/rest-api/reference/models/element.md!}

### Properties
{!developer/rest-api/reference/models/contentproperties.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
