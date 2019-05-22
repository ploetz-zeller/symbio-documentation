# Elements list

**api-version**: 2.0

Retrieves the list of elements.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements?$filter={filter}&$select={select}&$expandRelated={expand}&$page={page}&$pageSize={pageSize}&$pageSelectionKey={pageSelectionKey}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| elementId | path | true | string | The ID of the element. |
| $filter | query | | string | |
| $resources | query | | string ["attributes", "related", "children", "content", "rootPath"] | The resources to include. If not specified all resources will be included. |
| $select | query | | string | A comma separated list of namesof the attributes/related contexts to include. |
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |
| $page | query | | integer| The page number. |
| $pageSize | query | | integer | The page size. |
| $pageSelectionKey | query | | string | The ID of the element whose page will be fetched. |

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
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the list of elements from the *tree* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements
```

#### Response (200 OK)
```json
{
    "count": 2,
    "elements": [
        {
            "facetName": "processes",
            "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "creationId": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "type": "processHouse",
            "attributes": {
                "name": {
                    "1031": "Prozesshaus",
                    "1033": "Process House"
                },
                "state1": {
                    "127": "show"
                }
            },
            "related": {
                "owner": [
                    {
                        "facetName": "users",
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            },
            "children": [
                {
                    "facetName": "processes",
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "facetName": "processes",
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                },
                {
                    "facetName": "processes",
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                },
                {
                    "facetName": "processes",
                    "id": "5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/5cb80f0d-d94f-4d05-8a64-1d98345d481c"
                }
            ],
            "content": [
                {
                    "facetName": "processes",
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "facetName": "processes",
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                },
                {
                    "facetName": "processes",
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                },
                {
                    "facetName": "processes",
                    "id": "5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/5cb80f0d-d94f-4d05-8a64-1d98345d481c"
                }
            ]
        },
        {
            "facetName": "processes",
            "id": "883669b6-83af-4ce9-b532-b0ba929bef71",
            "type": "view",
            "attributes": {
                "name": {
                    "1031": "View",
                    "1033": "View"
                },
                "state1": {
                    "127": "show"
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
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            },
            "children": [
                {
                    "facetName": "processes",
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/c6e90187-b9f6-4787-9932-abfea54f5463"
                },
                {
                    "facetName": "processes",
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                },
                {
                    "facetName": "processes",
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/8db17967-8d30-4b75-9eab-434e85bd7df3"
                },
                {
                    "facetName": "processes",
                    "id": "77181a8e-b6fd-4176-929a-8cafded96cbb",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/77181a8e-b6fd-4176-929a-8cafded96cbb"
                }
            ],
            "content": [
                {
                    "facetName": "processes",
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c6e90187-b9f6-4787-9932-abfea54f5463"
                },
                {
                    "facetName": "processes",
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                },
                {
                    "facetName": "processes",
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8db17967-8d30-4b75-9eab-434e85bd7df3"
                },
                {
                    "facetName": "processes",
                    "id": "77181a8e-b6fd-4176-929a-8cafded96cbb",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/77181a8e-b6fd-4176-929a-8cafded96cbb"
                }
            ]
        }
    ]
}
```

### Get the list of elements from the *tree* view of the *processes* facet with the resources *attributes* and *children*

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements?$resources=attributes,children
```

#### Response (200 OK)
```json
{
    "count": 2,
    "elements": [
        {
            "facetName": "processes",
            "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "creationId": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "type": "processHouse",
            "attributes": {
                "name": {
                    "1031": "Prozesshaus",
                    "1033": "Process House"
                },
                "state1": {
                    "127": "show"
                }
            },
            "children": [
                {
                    "facetName": "processes",
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "facetName": "processes",
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                },
                {
                    "facetName": "processes",
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                },
                {
                    "facetName": "processes",
                    "id": "5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/5cb80f0d-d94f-4d05-8a64-1d98345d481c"
                }
            ]
        },
        {
            "facetName": "processes",
            "id": "883669b6-83af-4ce9-b532-b0ba929bef71",
            "type": "view",
            "attributes": {
                "name": {
                    "1031": "View",
                    "1033": "View"
                },
                "state1": {
                    "127": "show"
                }
            },
            "children": [
                {
                    "facetName": "processes",
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/c6e90187-b9f6-4787-9932-abfea54f5463"
                },
                {
                    "facetName": "processes",
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                },
                {
                    "facetName": "processes",
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/8db17967-8d30-4b75-9eab-434e85bd7df3"
                },
                {
                    "facetName": "processes",
                    "id": "77181a8e-b6fd-4176-929a-8cafded96cbb",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/77181a8e-b6fd-4176-929a-8cafded96cbb"
                }
            ]
        }
    ]
}
```

### Get the list of elements from the *detail* view of the *products* facet which are paginated. Result will return first page with 5 elements.

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/products/views/detail/elements?$page=1&$pageSize=5
```

#### Response (200 OK)
```json
{
    "count": 5,
    "elements": [
        {
            "facetName": "products",
            "id": "db73e2d6-445c-44d8-ba35-5015be48ab3f",
            "versionId": "81ca054c-5ab8-47d8-aa4a-0c39b551d5d7",
            "type": "product",
            "state": "inProcess",
            "stereotype": "74cc3ec4-b029-4f31-b0e4-8fd0368028ec",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-06-29T14:43:30"
                },
                "createdOn": {
                    "127": "2018-06-28T09:52:10"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Products/personalizedgraphic/81ca054c-5ab8-47d8-aa4a-0c39b551d5d7",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Products/personalizedgraphic/81ca054c-5ab8-47d8-aa4a-0c39b551d5d7"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Sicherheitscheck",
                    "1033": "Security check"
                },
                "state1": {
                    "127": "inProcess"
                },
                "stereotype": {
                    "127": "74cc3ec4-b029-4f31-b0e4-8fd0368028ec"
                },
                "validUntil": {
                    "127": "2019-06-28T00:00:00"
                },
                "version": {
                    "127": "0.1"
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
                "changedBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "createdBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ]
            }
        },
        {
            "facetName": "products",
            "id": "65ad489f-d385-4d4c-b059-0336b8758d44",
            "versionId": "9c4282b3-f1bb-4d7d-b909-b3dd5ed04121",
            "type": "product",
            "state": "inProcess",
            "stereotype": "74cc3ec4-b029-4f31-b0e4-8fd0368028ec",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-06-29T14:42:36"
                },
                "createdOn": {
                    "127": "2018-06-28T09:54:46"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Products/personalizedgraphic/9c4282b3-f1bb-4d7d-b909-b3dd5ed04121",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Products/personalizedgraphic/9c4282b3-f1bb-4d7d-b909-b3dd5ed04121"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Großkunden und Unternehmen",
                    "1033": "Grokunden and company"
                },
                "state1": {
                    "127": "inProcess"
                },
                "stereotype": {
                    "127": "74cc3ec4-b029-4f31-b0e4-8fd0368028ec"
                },
                "validUntil": {
                    "127": "2019-06-28T00:00:00"
                },
                "version": {
                    "127": "0.1"
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
                "changedBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "createdBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ]
            }
        },
        {
            "facetName": "products",
            "id": "23f68bea-ce13-4cf7-b718-f5d65962fd86",
            "versionId": "d0f7a0a8-a0ec-4f65-9fd2-1f9f0dcaaa8f",
            "type": "product",
            "state": "inProcess",
            "stereotype": "9ec2e51b-e933-4a4c-9eff-870ba624462b",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-07-02T13:36:42"
                },
                "createdOn": {
                    "127": "2018-06-28T09:43:44"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Products/personalizedgraphic/d0f7a0a8-a0ec-4f65-9fd2-1f9f0dcaaa8f",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Products/personalizedgraphic/d0f7a0a8-a0ec-4f65-9fd2-1f9f0dcaaa8f"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Dynamos",
                    "1033": "Dynamos"
                },
                "state1": {
                    "127": "inProcess"
                },
                "stereotype": {
                    "127": "9ec2e51b-e933-4a4c-9eff-870ba624462b"
                },
                "validUntil": {
                    "127": "2019-06-28T00:00:00"
                },
                "version": {
                    "127": "0.1"
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
                "changedBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "createdBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ]
            }
        },
        {
            "facetName": "products",
            "id": "8414869f-145d-4e37-a61a-08f111208188",
            "versionId": "aae105f6-fc92-444d-8d3f-07f0adaeb503",
            "type": "product",
            "state": "inProcess",
            "stereotype": "74cc3ec4-b029-4f31-b0e4-8fd0368028ec",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-07-02T13:26:38"
                },
                "createdOn": {
                    "127": "2018-06-29T12:21:16"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Products/personalizedgraphic/aae105f6-fc92-444d-8d3f-07f0adaeb503",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Products/personalizedgraphic/aae105f6-fc92-444d-8d3f-07f0adaeb503"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Ersatzteile",
                    "1033": "Spare parts"
                },
                "state1": {
                    "127": "inProcess"
                },
                "stereotype": {
                    "127": "74cc3ec4-b029-4f31-b0e4-8fd0368028ec"
                },
                "validUntil": {
                    "127": "2019-06-29T00:00:00"
                },
                "version": {
                    "127": "0.1"
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
                "changedBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "createdBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ]
            }
        },
        {
            "facetName": "products",
            "id": "d2f0097b-21ad-461d-8f7f-6a0ee44f6c24",
            "versionId": "a343b47d-b890-4ae0-bddd-225cabcc8e27",
            "type": "product",
            "state": "inProcess",
            "stereotype": "9ec2e51b-e933-4a4c-9eff-870ba624462b",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-07-02T13:33:55"
                },
                "createdOn": {
                    "127": "2018-06-28T09:46:54"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Products/personalizedgraphic/a343b47d-b890-4ae0-bddd-225cabcc8e27",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Products/personalizedgraphic/a343b47d-b890-4ae0-bddd-225cabcc8e27"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Hosen",
                    "1033": "Pants"
                },
                "state1": {
                    "127": "inProcess"
                },
                "stereotype": {
                    "127": "9ec2e51b-e933-4a4c-9eff-870ba624462b"
                },
                "validUntil": {
                    "127": "2019-06-28T00:00:00"
                },
                "version": {
                    "127": "0.1"
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
                "changedBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "createdBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ]
            }
        }
    ]
}
```

### Get the list of storage collections

!!! info
    This call only works on the *_sysadmin* collection and *_admin* storage.

#### Request
```
POST https://demo.symbioworld.com/_sysadmin/_admin/_api/rest/facets/collections/views/list/elements
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "id": "0c0f489a-bc63-4f75-ac0b-054f33083878",
            "type": "collection",
            "attributes": {
                "id": {
                    "127": "pz"
                },
                "name": {
                    "1031": "pz",
                    "1033": "pz"
                }
            }
        }
    ]
}
```

### Get the list of storages of a specific collection

!!! info
    This call only works on the *_admin* storage.

#### Request
```
POST https://demo.symbioworld.com/pz/_admin/_api/rest/facets/storages/views/detail/elements
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "id": "b028e1b3-88e8-4564-be04-bb9f204c842b",
            "type": "storage",
            "attributes": {
                "changedOn": {
                    "127": "2018-03-07T10:09:41"
                },
                "createdOn": {
                    "127": "2018-03-07T10:09:06"
                },
                "id": {
                    "127": "showcase"
                },
                "name": {
                    "1031": "showcase",
                    "1033": "showcase"
                }
            },
            "related": {
                "changedBy": [
                    {
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioweb.com/pz/_admin/Master_api/rest/facets/Users/views/List/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "createdBy": [
                    {
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioweb.com/pz/_admin/Master_api/rest/facets/Users/views/List/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
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
