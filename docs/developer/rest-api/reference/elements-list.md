---
uid: elementslist
---
# Elements

**api-version**: 1.0

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
| values | [Element[]](#element) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the list of elements from the *tree* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements
```

#### Reponse (200 OK)
```json
{
    "count": 2,
    "values": [
        {
            "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "type": "processHouse",
            "attributes": {
                "name": {
                    "1031": "Prozesshaus",
                    "1033": "Process House"
                },
                "state1": {
                    "127": "ValueType.AVTX_SHOW.ApiName"
                }
            },
            "related": {
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            },
            "children": [
                {
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                },
                {
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                },
                {
                    "id": "9af65492-279c-414d-960b-9a3cdf552142",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/9af65492-279c-414d-960b-9a3cdf552142"
                }
            ],
            "content": [
                {
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                },
                {
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                },
                {
                    "id": "9af65492-279c-414d-960b-9a3cdf552142",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/9af65492-279c-414d-960b-9a3cdf552142"
                }
            ]
        },
        {
            "id": "883669b6-83af-4ce9-b532-b0ba929bef71",
            "type": "view",
            "attributes": {
                "name": {
                    "1031": "Views",
                    "1033": "Views"
                },
                "state1": {
                    "127": "ValueType.AVTX_SHOW.ApiName"
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
            },
            "children": [
                {
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/c6e90187-b9f6-4787-9932-abfea54f5463"
                },
                {
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                },
                {
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/8db17967-8d30-4b75-9eab-434e85bd7df3"
                }
            ],
            "content": [
                {
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/c6e90187-b9f6-4787-9932-abfea54f5463"
                },
                {
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                },
                {
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/8db17967-8d30-4b75-9eab-434e85bd7df3"
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

#### Reponse (200 OK)
```json
{
    "count": 2,
    "values": [
        {
            "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "type": "processHouse",
            "attributes": {
                "name": {
                    "1031": "Prozesshaus",
                    "1033": "Process House"
                },
                "state1": {
                    "127": "ValueType.AVTX_SHOW.ApiName"
                }
            },
            "children": [
                {
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                },
                {
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                },
                {
                    "id": "9af65492-279c-414d-960b-9a3cdf552142",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/9af65492-279c-414d-960b-9a3cdf552142"
                }
            ]
        },
        {
            "id": "883669b6-83af-4ce9-b532-b0ba929bef71",
            "type": "view",
            "attributes": {
                "name": {
                    "1031": "Views",
                    "1033": "Views"
                },
                "state1": {
                    "127": "ValueType.AVTX_SHOW.ApiName"
                }
            },
            "children": [
                {
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/c6e90187-b9f6-4787-9932-abfea54f5463"
                },
                {
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                },
                {
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/8db17967-8d30-4b75-9eab-434e85bd7df3"
                }
            ]
        }
    ]
}
```

### Get the list of storage collections

> [!NOTE] 
> This call only works on the *_sysadmin* collection and *_admin* storage.

#### Request
```
POST https://demo.symbioworld.com/_sysadmin/_admin/_api/rest/facets/collections/views/list/elements
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
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

> [!NOTE] 
> This call only works on the *_admin* storage.

#### Request
```
POST https://demo.symbioworld.com/pz/_admin/_api/rest/facets/storages/views/detail/elements
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
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
[!include[](models\element.md)]

### OperationResultType 
[!include[](models\operationresulttype.md)]

### Error
[!include[](models\error.md)]
