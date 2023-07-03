# Children

**api-version**: 4.0

Retrieves the children of an element.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/children
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
| values | [ElementCollection](#element) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresulttype) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the children of an element

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/81a90000-84e3-4eef-9248-d62fd3bc8f62/children
```

#### Response (200 OK)
```json
{
    "count": 4,
    "elements": [
        {
            "facetName": "processes",
            "id": "42bb2b6b-a8ac-46d3-bfbe-ef89ec40c59f",
            "versionId": "e1da5e04-beea-46f7-93ad-b65b80caf0a3",
            "type": "mainProcess",
            "state": "inEffect",
            "displayNames": {
            "1031": "Main Process",
            "1033": "main process"
            },
            "attributes": {
                "name": {
                    "1031": "Customer/Partner Care",
                    "1033": "Customer/\nPartner Care"
                },
                "state1": {
                    "127": "inEffect"
                },
                "version": {
                    "127": "2.0"
                }
            },
            "related": {
                "author": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "owner": [
                    {
                        "facetName": "users",
                        "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "creationId": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/30fe276f-5312-45e2-ac9d-937437dcbc28"
                    }
                ]
            }
        },
        {
            "facetName": "processes",
            "id": "9b943f0e-8920-4456-afce-d8eba500f186",
            "versionId": "352f13f2-8ce5-4aec-a4ca-5b096f47e6a2",
            "type": "mainProcess",
            "state": "inEffect",
            "displayNames": {
            "1031": "Main Process",
            "1033": "main process"
            },
            "attributes": {
                "name": {
                    "1031": "Sales Planning",
                    "1033": "Sales Planning"
                },
                "state1": {
                    "127": "inEffect"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "facetName": "users",
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "facetName": "users",
                        "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "creationId": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/30fe276f-5312-45e2-ac9d-937437dcbc28"
                    }
                ]
            }
        },
        {
            "facetName": "processes",
            "id": "74d193aa-1ec7-44f4-a8cc-a213ee44a7a2",
            "versionId": "5cb4fae5-06e0-4efe-a5fd-27b904dc9736",
            "type": "mainProcess",
            "state": "inEffect",
            "displayNames": {
            "1031": "Main Process",
            "1033": "main process"
            },
            "attributes": {
                "name": {
                    "1031": "Sell Products/Solutions",
                    "1033": "Sell Products/\nSolutions"
                },
                "state1": {
                    "127": "inEffect"
                },
                "version": {
                    "127": "2.0"
                }
            },
            "related": {
                "author": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "owner": [
                    {
                        "facetName": "users",
                        "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "creationId": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/30fe276f-5312-45e2-ac9d-937437dcbc28"
                    }
                ]
            }
        },
        {
            "facetName": "processes",
            "id": "2f85c039-3c41-4c20-9a46-9ca48291671e",
            "versionId": "7ae0c5dc-7e49-44c2-8ed3-9982e4079ad8",
            "type": "mainProcess",
            "state": "inEffect",
            "displayNames": {
            "1031": "Main Process",
            "1033": "main process"
            },
            "attributes": {
                "name": {
                    "1031": "Understand Market/Customer",
                    "1033": "Understand Market/Customer"
                },
                "state1": {
                    "127": "inEffect"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "facetName": "users",
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "facetName": "users",
                        "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "creationId": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/30fe276f-5312-45e2-ac9d-937437dcbc28"
                    }
                ]
            }
        }
    ]
}
```

## Definitions

### Element
{!developer/rest-api/reference/models/element.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
