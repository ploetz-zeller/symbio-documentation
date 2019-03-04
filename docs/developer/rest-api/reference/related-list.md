---
uid: relatedlist
---
# List

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
| values | [Element[]](#element) | The list of related elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the list of related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/related
```

#### Reponse (200 OK)
```json
{
    "count": 26,
    "values": {
        "author": [
            {
                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/ab01a052-80f2-4fbf-8e21-698cb7095b34/List"
            }
        ],
        "changedBy": [
            {
                "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/a364f30b-a126-4a74-9e1a-1df87f2a6074/List"
            }
        ],
        "guidelines": [
            {
                "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                "type": "knowledgeStructureDocument",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/KnowledgeStructure/0da36332-3ae6-4127-9fb6-6853dbb7245b/PersonalizedArchitecture"
            },
            {
                "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                "type": "knowledgeStructureDocument",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/KnowledgeStructure/c337213a-7585-48a9-9eb2-cff2f9560011/PersonalizedArchitecture"
            }
        ],
        "hasInput": [
            {
                "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/d23564c5-567b-4439-940e-0efe9b140229/PersonalizedList"
            },
            {
                "id": "032a3501-4679-4cce-abc6-788394729bf9",
                "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/3887b540-3670-4f7a-b0b9-c4de9a5e004e/PersonalizedList"
            },
            {
                "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/2b251a32-afd8-4140-8406-9bf700189f33/PersonalizedList"
            },
            {
                "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/15dcc40d-fb65-494f-9d00-8c537f408347/PersonalizedList"
            },
            {
                "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/f6abd383-6a10-4470-b031-99df5748f4d0/PersonalizedList"
            }
        ],
        "hasOutput": [
            {
                "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6/PersonalizedList"
            },
            {
                "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3/PersonalizedList"
            },
            {
                "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b/PersonalizedList"
            },
            {
                "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/b5d63e65-6343-42fd-af6f-7d12ee3dc13d/PersonalizedList"
            },
            {
                "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/dd5eced4-9771-414f-a8b6-ffd29523d041/PersonalizedList"
            },
            {
                "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/ac167362-c4c2-4407-a423-00c43e0a7069/PersonalizedList"
            }
        ],
        "kpi": [
            {
                "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                "type": "kPI",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/PerformanceIndicators/657ab3f7-165b-4dc5-9821-52ef417061eb/PersonalizedList"
            },
            {
                "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                "type": "kPI",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/PerformanceIndicators/90955400-f199-11df-2459-ccb6a833f624/PersonalizedList"
            }
        ],
        "nonFilteredGuidelines": [
            {
                "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                "type": "knowledgeStructureDocument",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/KnowledgeStructure/0da36332-3ae6-4127-9fb6-6853dbb7245b/PersonalizedArchitecture"
            },
            {
                "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                "type": "knowledgeStructureDocument",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/KnowledgeStructure/c337213a-7585-48a9-9eb2-cff2f9560011/PersonalizedArchitecture"
            }
        ],
        "nonFilteredHasInput": [
            {
                "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/d23564c5-567b-4439-940e-0efe9b140229/PersonalizedList"
            },
            {
                "id": "032a3501-4679-4cce-abc6-788394729bf9",
                "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/3887b540-3670-4f7a-b0b9-c4de9a5e004e/PersonalizedList"
            },
            {
                "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/2b251a32-afd8-4140-8406-9bf700189f33/PersonalizedList"
            },
            {
                "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/15dcc40d-fb65-494f-9d00-8c537f408347/PersonalizedList"
            },
            {
                "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/f6abd383-6a10-4470-b031-99df5748f4d0/PersonalizedList"
            }
        ],
        "nonFilteredHasOutput": [
            {
                "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6/PersonalizedList"
            },
            {
                "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3/PersonalizedList"
            },
            {
                "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b/PersonalizedList"
            },
            {
                "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/b5d63e65-6343-42fd-af6f-7d12ee3dc13d/PersonalizedList"
            },
            {
                "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/dd5eced4-9771-414f-a8b6-ffd29523d041/PersonalizedList"
            },
            {
                "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                "type": "inOut",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/InputsOutputs/ac167362-c4c2-4407-a423-00c43e0a7069/PersonalizedList"
            }
        ],
        "nonFilteredKpi": [
            {
                "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                "type": "kPI",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/PerformanceIndicators/657ab3f7-165b-4dc5-9821-52ef417061eb/PersonalizedList"
            },
            {
                "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                "type": "kPI",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/PerformanceIndicators/90955400-f199-11df-2459-ccb6a833f624/PersonalizedList"
            }
        ],
        "nonFilteredRequirements": [
            {
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Requirements/1d5545cd-7d23-4d96-b89b-e44bf176623e/PersonalizedArchitecture"
            },
            {
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Requirements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b/PersonalizedArchitecture"
            }
        ],
        "nonFilteredRisks": [
            {
                "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                "type": "risk",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/RiskStructure/6076b42b-2ff5-4cb6-a353-9e996a368922/PersonalizedArchitecture"
            }
        ],
        "nonFilteredSecondarySystemsInput": [
            {
                "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/fb925a60-65f7-44de-bef1-e1a23b9cdd4e/PersonalizedArchitecture"
            }
        ],
        "nonFilteredSecondarySystemsOutput": [
            {
                "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e/PersonalizedArchitecture"
            },
            {
                "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                "versionId": "ada5da3f-fa08-4944-9c5e-49a52a7f86dc",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/ada5da3f-fa08-4944-9c5e-49a52a7f86dc/PersonalizedArchitecture"
            }
        ],
        "nonFilteredSystems": [
            {
                "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a/PersonalizedArchitecture"
            }
        ],
        "nonFilteredTrainings": [
            {
                "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                "type": "training",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Trainings/aa346082-cfc1-4695-accc-a1673947987b/PersonalizedList"
            }
        ],
        "organisations": [
            {
                "id": "43320ec1-1d8b-46b8-93e1-037a2d61d208",
                "versionId": "171fe695-8776-49fc-9fda-ac37a1728299",
                "type": "orgUnit",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Organization/171fe695-8776-49fc-9fda-ac37a1728299/Architecture"
            }
        ],
        "persResp": [
            {
                "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/0630c057-6ba7-47fd-a72f-c9bb80bf18b1/List"
            }
        ],
        "qualityManager": [
            {
                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/45b86897-4509-4db3-953f-bf4998f86f4d/List"
            }
        ],
        "releaseHistory": [
            {
                "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
                "versionId": "9fe36070-f0c0-11df-4e21-001c25729284",
                "type": "subProcess",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/9fe36070-f0c0-11df-4e21-001c25729284/TreeAndDiagram"
            }
        ],
        "requirements": [
            {
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Requirements/1d5545cd-7d23-4d96-b89b-e44bf176623e/PersonalizedArchitecture"
            },
            {
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Requirements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b/PersonalizedArchitecture"
            }
        ],
        "risks": [
            {
                "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                "type": "risk",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/RiskStructure/6076b42b-2ff5-4cb6-a353-9e996a368922/PersonalizedArchitecture"
            }
        ],
        "secondarySystemsInput": [
            {
                "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/fb925a60-65f7-44de-bef1-e1a23b9cdd4e/PersonalizedArchitecture"
            }
        ],
        "secondarySystemsOutput": [
            {
                "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e/PersonalizedArchitecture"
            },
            {
                "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                "versionId": "ada5da3f-fa08-4944-9c5e-49a52a7f86dc",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/ada5da3f-fa08-4944-9c5e-49a52a7f86dc/PersonalizedArchitecture"
            }
        ],
        "systems": [
            {
                "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                "type": "system",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/ITArchitecture/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a/PersonalizedArchitecture"
            }
        ],
        "trainings": [
            {
                "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                "type": "training",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Trainings/aa346082-cfc1-4695-accc-a1673947987b/PersonalizedList"
            }
        ]
    }
}
```

### Get the *author* and *requirements* related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/related?$select=author,requirements
```

#### Reponse (200 OK)
```json
{
    "count": 2,
    "values": {
        "author": [
            {
                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Users/ab01a052-80f2-4fbf-8e21-698cb7095b34/List"
            }
        ],
        "requirements": [
            {
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Requirements/1d5545cd-7d23-4d96-b89b-e44bf176623e/PersonalizedArchitecture"
            },
            {
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Requirements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b/PersonalizedArchitecture"
            }
        ]
    }
}
```

### Get and expand the *author* and *requirements* related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/related?$select=author,requirements&$expandRelated=author,requirements
```

#### Reponse (200 OK)
```json
{
    "count": 2,
    "values": {
        "author": [
            {
                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
            }
        ],
        "requirements": [
            {
                "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e",
                "related": {
                    "author": [
                        {
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user",
                            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                        }
                    ]
                }
            },
            {
                "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "type": "requirement",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                "related": {
                    "author": [
                        {
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user",
                            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
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
