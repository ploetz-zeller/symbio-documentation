# Related list

**api-version**: 1.0

Retrieves the list of related contexts.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/related
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/related?$filter={filter}&$select={select}&$expandRelated={expand}
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
| $select | query | | string | A comma separated list of namesof the attributes/related contexts to include. |
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [ElementCollection](#element) | The list of related elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the list of related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/related
```

#### Response (200 OK)
```json
{
    "count": 18,
    "values": {
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
        ],
        "guidelines": [
            {
                "facetName": "knowledge",
                "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                "type": "knowledgeStructureDocument",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/knowledge/views/detail/elements/c337213a-7585-48a9-9eb2-cff2f9560011"
            },
            {
                "facetName": "knowledge",
                "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                "type": "knowledgeStructureDocument",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/knowledge/views/detail/elements/0da36332-3ae6-4127-9fb6-6853dbb7245b"
            }
        ],
        "hasInput": [
            {
                "facetName": "inputsoutputs",
                "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                "type": "inOut",
                "state": "released",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/d23564c5-567b-4439-940e-0efe9b140229"
            },
            {
                "facetName": "inputsoutputs",
                "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/15dcc40d-fb65-494f-9d00-8c537f408347"
            },
            {
                "facetName": "inputsoutputs",
                "id": "032a3501-4679-4cce-abc6-788394729bf9",
                "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                "type": "inOut",
                "state": "released",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/3887b540-3670-4f7a-b0b9-c4de9a5e004e"
            },
            {
                "facetName": "inputsoutputs",
                "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/2b251a32-afd8-4140-8406-9bf700189f33"
            },
            {
                "facetName": "inputsoutputs",
                "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                "type": "inOut",
                "state": "released",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/f6abd383-6a10-4470-b031-99df5748f4d0"
            }
        ],
        "hasOutput": [
            {
                "facetName": "inputsoutputs",
                "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/dd5eced4-9771-414f-a8b6-ffd29523d041"
            },
            {
                "facetName": "inputsoutputs",
                "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b"
            },
            {
                "facetName": "inputsoutputs",
                "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/b5d63e65-6343-42fd-af6f-7d12ee3dc13d"
            },
            {
                "facetName": "inputsoutputs",
                "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3"
            },
            {
                "facetName": "inputsoutputs",
                "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                "type": "inOut",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/ac167362-c4c2-4407-a423-00c43e0a7069"
            },
            {
                "facetName": "inputsoutputs",
                "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                "type": "inOut",
                "state": "released",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6"
            }
        ],
        "kpi": [
            {
                "facetName": "kpi",
                "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                "type": "kPI",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/kpi/views/detail/elements/90955400-f199-11df-2459-ccb6a833f624"
            },
            {
                "facetName": "kpi",
                "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                "type": "kPI",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/kpi/views/detail/elements/657ab3f7-165b-4dc5-9821-52ef417061eb"
            }
        ],
        "organizationFilters": [
            {
                "facetName": "organization",
                "id": "43320ec1-1d8b-46b8-93e1-037a2d61d208",
                "versionId": "171fe695-8776-49fc-9fda-ac37a1728299",
                "type": "orgUnit",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/organization/views/detail/elements/171fe695-8776-49fc-9fda-ac37a1728299",
                "stereotype": "division"
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
        ],
        "qualityManager": [
            {
                "facetName": "users",
                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/45b86897-4509-4db3-953f-bf4998f86f4d"
            }
        ],
        "releaseHistory": [
            {
                "facetName": "processes",
                "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
                "versionId": "9fe36070-f0c0-11df-4e21-001c25729284",
                "type": "subProcess",
                "state": "expired",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9fe36070-f0c0-11df-4e21-001c25729284"
            },
            {
                "facetName": "processes",
                "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
                "versionId": "168c8bc4-779e-4697-8334-0026411d52f1",
                "type": "subProcess",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1"
            }
        ],
        "requirements": [
            {
                "facetName": "requirements",
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views/detail/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
            },
            {
                "facetName": "requirements",
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views/detail/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
            }
        ],
        "risks": [
            {
                "facetName": "risks",
                "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                "type": "risk",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/risks/views/detail/elements/6076b42b-2ff5-4cb6-a353-9e996a368922"
            }
        ],
        "secondarySystemsInput": [
            {
                "facetName": "it",
                "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                "type": "system",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/detail/elements/fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                "stereotype": "applicationSystem"
            }
        ],
        "secondarySystemsOutput": [
            {
                "facetName": "it",
                "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                "type": "system",
                "state": "released",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/detail/elements/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                "stereotype": "applicationSystem"
            },
            {
                "facetName": "it",
                "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                "versionId": "ea285079-365b-4e59-88f4-e85b6c1518c4",
                "type": "system",
                "state": "released",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/detail/elements/ea285079-365b-4e59-88f4-e85b6c1518c4",
                "stereotype": "applicationSystem"
            }
        ],
        "systems": [
            {
                "facetName": "it",
                "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                "type": "system",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/detail/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                "stereotype": "applicationSystem"
            }
        ],
        "tagFilters": [
            {
                "facetName": "tags",
                "id": "b5606290-178e-43ae-837a-f2fd149e4ea9",
                "creationId": "b5606290-178e-43ae-837a-f2fd149e4ea9",
                "type": "tag",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/tags/views/detail/elements/b5606290-178e-43ae-837a-f2fd149e4ea9"
            }
        ],
        "trainings": [
            {
                "facetName": "learning",
                "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                "type": "training",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/learning/views/detail/elements/aa346082-cfc1-4695-accc-a1673947987b",
                "stereotype": "elearning"
            }
        ]
    }
}
```

### Get the *author* and *requirements* related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/related?$select=author,requirements
```

#### Response (200 OK)
```json
{
    "count": 2,
    "values": {
        "author": [
            {
                "facetName": "users",
                "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
            }
        ],
        "requirements": [
            {
                "facetName": "requirements",
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views/detail/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
            },
            {
                "facetName": "requirements",
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views/detail/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
            }
        ]
    }
}
```

### Get and expand the *author* and *requirements* related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/related?$select=author,requirements&$expandRelated=author,requirements
```

#### Response (200 OK)
```json
{
    "count": 2,
    "values": {
        "author": [
            {
                "facetName": "users",
                "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
            }
        ],
        "requirements": [
            {
                "facetName": "requirements",
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views/detail/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "related": {
                    "author": [
                        {
                            "facetName": "users",
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user"
                        }
                    ]
                }
            },
            {
                "facetName": "requirements",
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "state": "inEffect",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views/detail/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "related": {
                    "author": [
                        {
                            "facetName": "users",
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user"
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

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
