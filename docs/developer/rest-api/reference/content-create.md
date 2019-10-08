# Content create

**api-version**: 3.0

Create content of an element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/diagram/elements/{elementId}/content
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
| type | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Create new content shapes in an element

#### Request

```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/db313e1c-9a5f-400e-add9-6282e3058dca/content
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

#### Response (200 OK)

```json
{
    "values":
    [
        {
            "id":"a2c0abae-6fbd-42a8-a7a9-931f41ac187d",
            "index":0
        },
            
        {
            "id":"fb92ff40-a84b-4879-bce0-0aa24982f23e",
            "index":1
        },
        {
            "id":"9807501f-e1da-41cf-9c31-91e4fa38be43",
            "index":2
        }
    ]
}
```

### Create a new content shape as successor of an existing shape

#### Request

```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/db313e1c-9a5f-400e-add9-6282e3058dca/content
```

### Request Body

```json
{
    "values": [
        {
            "shapeInfo": {
                "index": 0,
                "id": "a2c0abae-6fbd-42a8-a7a9-931f41ac187d"
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

#### Response (200 OK)

```json
{
    "values":
        [
            {
                "id": "fc1388c1-9956-4028-9603-2954a24a377d",
                "index": 0
            },
            {
                "id": "ec10b6fd-1e47-4c90-9992-f3654166d444",
                "index": 
            }
        ]
}
```

### Create a new content shape and reference an existing SubProcess

#### Request

```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/elements/db313e1c-9a5f-400e-add9-6282e3058dca/content
```

### Request Body

```json
{
    "values": [
        {
            "shapeInfo": {
                "index": 0,
                "id": "a2c0abae-6fbd-42a8-a7a9-931f41ac187d"
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
                "id": "db313e1c-9a5f-400e-add9-6282e3058dca"
            }
        }
    ]
}
```

#### Response (200 OK)

```json
{
    "values":
        [
            {
                "id": "fc1388c1-9956-4028-9603-2954a24a377d",
                "index": 0
            },
            {
                "id": "db313e1c-9a5f-400e-add9-6282e3058dca",
                "index": 
            }
        ]
}
```

## Definitions

### Element

{!developer/rest-api/reference/models/element.md!}

### ContentModel

{!developer/rest-api/reference/models/contentmodel.md!}

### ContentShapeInfo

{!developer/rest-api/reference/models/contentshapeinfo.md!}

### OperationResultOutput

{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType

{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError

{!developer/rest-api/reference/models/operationerror.md!}
