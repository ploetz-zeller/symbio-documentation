# Content - Create

**api-version**: 3.0

Create content of an element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/content
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| elementId | path | true | string | The ID of the element. |

## Request Body

| Name | Type | Description |
|---|---|---|
| values | [ContentModel[]](#contentmodel) | A collection of content models. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| output | string | |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Create new content shapes in an element

#### Request

```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/1a526d30-f0c4-11df-4e21-001c25729284/content
```

### Request Body

```json
{
    "values": [
        {
            "shapeInfo": {
                "index": 0
            },
            "element": {
                "type": "evStart",
                "attributes": {
                    "name": {
                        "1031": "Start"
                    }
                }
            }
        },
        {
            "shapeInfo": {
                "predecessors": [
                    0
                ],
                "index": 1
            },
            "element": {
                "type": "subProcess",
                "attributes": {
                    "name": {
                        "1031": "SubProcess"
                    }
                }
            }
        },
        {
            "shapeInfo": {
                "predecessors": [
                    1
                ],
                "index": 2
            },
            "element": {
                "type": "evEnd",
                "attributes": {
                    "name": {
                        "1031": "End"
                    }
                }
            }
        }
    ]
}
```

#### Reponse (200 OK)

```json
{
    "message": "",
    "output": "Volatile",
    "type": "Success"
}
```

### Create a new content shape as successor of an existing shape

#### Request

```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/1a526d30-f0c4-11df-4e21-001c25729284/content
```

### Request Body

```json
{
    "values": [
        {
            "shapeInfo": {
                "index": 0,
                "id": "a7bbe7cb-c8a1-412c-822c-770ce4854fb7"
            }
        },
        {
            "shapeInfo": {
                "predecessors": [
                    0
                ],
                "index": 1
            },
            "element": {
                "type": "task",
                "attributes": {
                    "name": {
                        "1031": "Task"
                    }
                }
            }
        }
    ]
}
```

#### Reponse (200 OK)

```json
{
    "message": "",
    "output": "Volatile",
    "type": "Success"
}
```

### Create a new content shape and reference an existing SubProcess

#### Request

```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/1a526d30-f0c4-11df-4e21-001c25729284/content
```

### Request Body

```json
{
    "values": [
        {
            "shapeInfo": {
                "index": 0,
                "id": "a7bbe7cb-c8a1-412c-822c-770ce4854fb7"
            }
        },
        {
            "shapeInfo": {
                "predecessors": [
                    0
                ],
                "index": 1
            },
            "element": {
                "type": "subProcess",
                "id": "e7774de1-9af3-40f0-9c66-58603e887993"
            }
        }
    ]
}
```

#### Reponse (200 OK)

```json
{
    "message": "",
    "output": "Volatile",
    "type": "Success"
}
```

## Definitions

### Element

{!developer/rest-api/reference/models/element.md!}

### ContentModel

{!developer/rest-api/reference/models/contentmodel.md!}

### ShapeInfo

{!developer/rest-api/reference/models/shapeinfo.md!}

### OperationResultType

{!developer/rest-api/reference/models/operationresulttype.md!}

### Error

{!developer/rest-api/reference/models/error.md!}
