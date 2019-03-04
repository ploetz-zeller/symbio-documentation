# Children

**api-version**: 1.0

Retrieves the children of an element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/children
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
| values | [Element[]](#element) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the children of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80/children
```

#### Reponse (200 OK)
```json
{
{
    "count": 6,
    "values": [
        {
            "id": "0d12c107-5b73-4afa-9636-cbc1a43f505e",
            "versionId": "87174e3c-466c-42e3-b227-5bcd427a01ea",
            "attributes": {
                "name": {
                    "1031": "Financial Planning & Controlling",
                    "1033": "Financial Planning & Controlling"
                },
                "state1": {
                    "127": "released"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            }
        },
        {
            "id": "d7b81b45-743e-4dd5-9fe4-94293ddde5e7",
            "versionId": "90d9eca8-dd55-44a9-9415-89d14b4a9131",
            "attributes": {
                "name": {
                    "1031": "Idea Management / Innovation",
                    "1033": "Idea Management / Innovation"
                },
                "state1": {
                    "127": "released"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/30fe276f-5312-45e2-ac9d-937437dcbc28"
                    }
                ]
            }
        },
        {
            "id": "f6c1a1bb-b53e-469e-bff2-d0166c239998",
            "versionId": "2b3dc6a3-be9a-4fd3-87d7-62a7c58cd028",
            "attributes": {
                "name": {
                    "1031": "Leadership",
                    "1033": "Leadership"
                },
                "state1": {
                    "127": "released"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            }
        },
        {
            "id": "8845fad0-6744-494d-98fb-07dfedc03f08",
            "versionId": "96dfcc40-5225-4940-ab02-0b95fd3e32e7",
            "attributes": {
                "name": {
                    "1031": "Management System",
                    "1033": "Management System"
                },
                "state1": {
                    "127": "released"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ]
            }
        },
        {
            "id": "3f37d7ab-b280-44f3-8ac6-2a60838cb8e4",
            "versionId": "377e74c8-74ae-4262-8676-cf9c26e49f7b",
            "attributes": {
                "name": {
                    "1031": "Risk & Compliance",
                    "1033": "Risk & Compliance"
                },
                "state1": {
                    "127": "released"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "owner": [
                    {
                        "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/30fe276f-5312-45e2-ac9d-937437dcbc28"
                    }
                ]
            }
        },
        {
            "id": "260955dd-f53b-4ccc-82e8-75a2c99e02d2",
            "versionId": "ba50fa20-0519-4c5a-b217-091d3edac599",
            "attributes": {
                "name": {
                    "1031": "Strategic Planning & Controlling",
                    "1033": "Strategic Planning & Controlling"
                },
                "state1": {
                    "127": "released"
                },
                "version": {
                    "127": "1.0"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
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

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
