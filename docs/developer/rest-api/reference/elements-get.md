# Elements

**api-version**: 1.0

Retrieves a specific element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}?$filter={filter}&$select={select}&$expandRelated={expand}
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
| $select | query | | string | A comma separated list of names of the attributes/related contexts to include. |
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |

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

### Get a specific element from the *detail* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "168c8bc4-779e-4697-8334-0026411d52f1",
            "attributes": {
                "changedOn": {
                    "127": "2018-03-07T10:15:40"
                },
                "createdOn": {
                    "127": "2007-12-03T00:00:00"
                },
                "description": {
                    "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>Der Innovations- und Anforderungsprozess gliedert sich in drei Phasen:</p><ul>\n<li>Impulsphase: Beobachtung von Trends, Ideenfindung, Brainstorming von Anforderungen, Kundenanforderungen</li>\n<li>Bewertungsphase: Prüfung auf Tauglichkeit der Idee für das jeweilige Produkt und den Marktanforderungen</li>\n<li>Technologietransfer: Anforderungen in die Release-Planung überführen</li>\n</ul></div>",
                    "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>The Innovation and request process is divided into three phases:</p><ul>\n<li>Pulse phase: review of trends, ideas, brainstorming of requirements, customer requirements</li>\n<li>Evaluation phase: testing for suitability of the idea for the product and market requirements</li>\n<li>Technology transfer: transfer requirements in the release planning</li>\n</ul></div>"
                },
                "name": {
                    "1031": "Ideen/Innovationen",
                    "1033": "Idea/Innovation"
                },
                "processMaturity": {
                    "127": "processIsLived"
                },
                "purp": {
                    "1031": "Qualifizierung eingegangener Ideen und Anforderungen. Unter dem Begriff Qualifizierung versteht man den Vorgang zur Erlangung von Fähigkeiten (Qualifikationen), um eine bestimmte Aufgabe oder Anforderung erfüllen zu können. Ebenso die Überprüfung dieser Fähigkeiten wird als Qualifizierung bezeichnet. Die Überprüfung, dass die Fähigkeiten ausreichen, um im praktischen Einsatz reproduzierbar die gestellten Anforderungen zu erfüllen, ist Inhalt der so genannten Validierung.",
                    "1033": "Qualification of received ideas and requirements. The term qualification is the process of obtaining skills (qualifications), to perform a specific task or requirement can. Similarly, the review of these abilities is called qualification. The verification that the skills sufficient to reproducibly meet the requirements in practical use, is content of the so-called validation."
                },
                "scope": {
                    "1031": "Komplettes Unternehmen",
                    "1033": "Complete company"
                },
                "state1": {
                    "127": "inProcess"
                },
                "validFrom": {
                    "127": "2015-12-01T18:39:48"
                },
                "validFromUntilPastMessage": {
                    "1031": "The date \"01.12.2015\" for \"Gültigkeitsstart\" is in the past.\r\nThe date \"31.03.2016\" for \"Gültigkeitsende\" is in the past.\r\n",
                    "1033": "The date \"12/1/2015\" for \"Start of Validity\" is in the past.\r\nThe date \"3/31/2016\" for \"End of Validity\" is in the past.\r\n"
                },
                "validUntil": {
                    "127": "2016-03-31T00:00:00"
                },
                "workshopImages": {
                    "127": [
                        {
                            "address": "18077efd-e887-4b26-841d-f2374d8da7c1",
                            "fullAddress": "https://demo.symbioworld.com/pz/showcase/Master/editor/1033/BasePlugin/File/GetFile/18077efd-e887-4b26-841d-f2374d8da7c1.Storage.html",
                            "mimeType": "image/jpeg",
                            "protocol": "Storage",
                            "title": "Idea-Innovation_klein"
                        }
                    ]
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
                "changedBy": [
                    {
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "guidelines": [
                    {
                        "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                        "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/0da36332-3ae6-4127-9fb6-6853dbb7245b"
                    },
                    {
                        "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                        "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/c337213a-7585-48a9-9eb2-cff2f9560011"
                    }
                ],
                "hasInput": [
                    {
                        "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                        "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/d23564c5-567b-4439-940e-0efe9b140229"
                    },
                    {
                        "id": "032a3501-4679-4cce-abc6-788394729bf9",
                        "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/3887b540-3670-4f7a-b0b9-c4de9a5e004e"
                    },
                    {
                        "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                        "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/2b251a32-afd8-4140-8406-9bf700189f33"
                    },
                    {
                        "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                        "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/15dcc40d-fb65-494f-9d00-8c537f408347"
                    },
                    {
                        "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                        "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/f6abd383-6a10-4470-b031-99df5748f4d0"
                    }
                ],
                "hasOutput": [
                    {
                        "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                        "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6"
                    },
                    {
                        "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                        "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3"
                    },
                    {
                        "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                        "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b"
                    },
                    {
                        "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                        "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/b5d63e65-6343-42fd-af6f-7d12ee3dc13d"
                    },
                    {
                        "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                        "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/dd5eced4-9771-414f-a8b6-ffd29523d041"
                    },
                    {
                        "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                        "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ac167362-c4c2-4407-a423-00c43e0a7069"
                    }
                ],
                "kpi": [
                    {
                        "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                        "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/657ab3f7-165b-4dc5-9821-52ef417061eb"
                    },
                    {
                        "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                        "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/90955400-f199-11df-2459-ccb6a833f624"
                    }
                ],
                "nonFilteredGuidelines": [
                    {
                        "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                        "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/0da36332-3ae6-4127-9fb6-6853dbb7245b"
                    },
                    {
                        "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                        "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/c337213a-7585-48a9-9eb2-cff2f9560011"
                    }
                ],
                "nonFilteredHasInput": [
                    {
                        "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                        "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/d23564c5-567b-4439-940e-0efe9b140229"
                    },
                    {
                        "id": "032a3501-4679-4cce-abc6-788394729bf9",
                        "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/3887b540-3670-4f7a-b0b9-c4de9a5e004e"
                    },
                    {
                        "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                        "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/2b251a32-afd8-4140-8406-9bf700189f33"
                    },
                    {
                        "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                        "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/15dcc40d-fb65-494f-9d00-8c537f408347"
                    },
                    {
                        "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                        "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/f6abd383-6a10-4470-b031-99df5748f4d0"
                    }
                ],
                "nonFilteredHasOutput": [
                    {
                        "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                        "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6"
                    },
                    {
                        "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                        "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3"
                    },
                    {
                        "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                        "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b"
                    },
                    {
                        "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                        "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/b5d63e65-6343-42fd-af6f-7d12ee3dc13d"
                    },
                    {
                        "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                        "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/dd5eced4-9771-414f-a8b6-ffd29523d041"
                    },
                    {
                        "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                        "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ac167362-c4c2-4407-a423-00c43e0a7069"
                    }
                ],
                "nonFilteredKpi": [
                    {
                        "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                        "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/657ab3f7-165b-4dc5-9821-52ef417061eb"
                    },
                    {
                        "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                        "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/90955400-f199-11df-2459-ccb6a833f624"
                    }
                ],
                "nonFilteredRequirements": [
                    {
                        "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                        "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
                    },
                    {
                        "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                        "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
                    }
                ],
                "nonFilteredRisks": [
                    {
                        "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                        "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                        "type": "risk",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/RiskStructure/views/PersonalizedArchitecture/elements/6076b42b-2ff5-4cb6-a353-9e996a368922"
                    }
                ],
                "nonFilteredSecondarySystemsInput": [
                    {
                        "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                        "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/fb925a60-65f7-44de-bef1-e1a23b9cdd4e"
                    }
                ],
                "nonFilteredSecondarySystemsOutput": [
                    {
                        "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                        "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e"
                    },
                    {
                        "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                        "versionId": "ada5da3f-fa08-4944-9c5e-49a52a7f86dc",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/ada5da3f-fa08-4944-9c5e-49a52a7f86dc"
                    }
                ],
                "nonFilteredSystems": [
                    {
                        "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                        "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a"
                    }
                ],
                "nonFilteredTrainings": [
                    {
                        "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                        "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                        "type": "training",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Trainings/views/PersonalizedList/elements/aa346082-cfc1-4695-accc-a1673947987b"
                    }
                ],
                "organisations": [
                    {
                        "id": "43320ec1-1d8b-46b8-93e1-037a2d61d208",
                        "versionId": "171fe695-8776-49fc-9fda-ac37a1728299",
                        "type": "orgUnit",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Organization/views/Architecture/elements/171fe695-8776-49fc-9fda-ac37a1728299"
                    }
                ],
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "qualityManager": [
                    {
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ],
                "releaseHistory": [
                    {
                        "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
                        "versionId": "9fe36070-f0c0-11df-4e21-001c25729284",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/9fe36070-f0c0-11df-4e21-001c25729284"
                    }
                ],
                "requirements": [
                    {
                        "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                        "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
                    },
                    {
                        "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                        "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
                    }
                ],
                "risks": [
                    {
                        "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                        "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                        "type": "risk",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/RiskStructure/views/PersonalizedArchitecture/elements/6076b42b-2ff5-4cb6-a353-9e996a368922"
                    }
                ],
                "secondarySystemsInput": [
                    {
                        "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                        "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/fb925a60-65f7-44de-bef1-e1a23b9cdd4e"
                    }
                ],
                "secondarySystemsOutput": [
                    {
                        "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                        "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e"
                    },
                    {
                        "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                        "versionId": "ada5da3f-fa08-4944-9c5e-49a52a7f86dc",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/ada5da3f-fa08-4944-9c5e-49a52a7f86dc"
                    }
                ],
                "systems": [
                    {
                        "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                        "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a"
                    }
                ],
                "trainings": [
                    {
                        "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                        "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                        "type": "training",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Trainings/views/PersonalizedList/elements/aa346082-cfc1-4695-accc-a1673947987b"
                    }
                ]
            },
            "content": [
                {
                    "id": "6ba15f74-9fad-4cbd-b51d-eb09255f9125",
                    "type": "func"
                },
                {
                    "id": "d567a583-6240-4e53-a8ab-6edc14482019",
                    "type": "ruleAnd"
                },
                {
                    "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                    "versionId": "664fd624-d341-4521-b430-897bb16399f4",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/664fd624-d341-4521-b430-897bb16399f4"
                },
                {
                    "id": "173f80e7-1b7f-4c4b-9266-ea8177c33267",
                    "type": "func"
                },
                {
                    "id": "8824f210-f0cf-4348-8bf9-3f3a1b7ade62",
                    "type": "func"
                },
                {
                    "id": "c8cc7945-2f18-4bda-b53c-934e0f29a17b",
                    "type": "func"
                },
                {
                    "id": "2c3abe5c-6c1f-4e3f-9db6-5fcda2ffeef1",
                    "type": "func"
                },
                {
                    "id": "850b13ec-a5cd-4d41-9ea1-7a508861d2b8",
                    "type": "evStart"
                },
                {
                    "id": "50f66862-90cb-42c6-9ccb-5a186f4c5259",
                    "type": "funcCondition"
                },
                {
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                {
                    "id": "e1cc7546-41de-40c9-9ebf-db3f8440de4f",
                    "type": "ruleAnd"
                },
                {
                    "id": "96ad0409-9018-4ebe-9bc2-8b1ba4edf7ef",
                    "type": "funcCondition"
                },
                {
                    "id": "731d1fb1-4e7b-4a51-8af1-58914db6f50b",
                    "type": "funcCondition"
                },
                {
                    "id": "1282b5f8-fd30-4e89-8d26-b7323b78d76d",
                    "type": "evIntermediate"
                },
                {
                    "id": "aefa209f-38d4-4895-abe7-f779b555c6ed",
                    "type": "ruleXor"
                },
                {
                    "id": "2c3601d2-aeb2-4c66-a936-1a8f660b1723",
                    "type": "ruleXor"
                },
                {
                    "id": "b80379bc-137e-40f7-a95e-3d5f4ec39aa4",
                    "type": "func"
                },
                {
                    "id": "3e8d271e-8538-46c3-a7d2-c40d90e588d4",
                    "type": "funcCondition"
                },
                {
                    "id": "070269f5-7b41-4d09-94ca-4b88fa518a32",
                    "type": "func"
                },
                {
                    "id": "07b12234-3eb1-4cdb-8973-26a0135b6549",
                    "type": "func"
                },
                {
                    "id": "a201a5cb-8ab9-4d6d-a5d6-f070b1922c17",
                    "type": "ruleXor"
                },
                {
                    "id": "fc2e9a36-239a-40e4-8caf-666f32e8ea9a",
                    "type": "func"
                },
                {
                    "id": "83adec24-87dc-4a42-b2b5-9025c704c0f6",
                    "type": "evEnd"
                },
                {
                    "id": "f2adfa58-3efc-4577-8d1c-0a787a6e947a",
                    "type": "func"
                },
                {
                    "id": "ceda130c-e979-4d2b-ac1f-1718c6e2e389",
                    "type": "funcCondition"
                },
                {
                    "id": "baf01625-3395-49cf-adbe-9ec4efcd18fe",
                    "type": "func"
                },
                {
                    "id": "5e625082-ffc0-43d5-843e-547f64fd447a",
                    "type": "func"
                },
                {
                    "id": "7fdd1a63-bcd5-414f-b16c-dce08a8328b8",
                    "type": "evEnd"
                }
            ]
        }
    ]
}
```

### Get a specific element from the *detail* view of the *processes* facet with the resources *attributes* and *related*

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "168c8bc4-779e-4697-8334-0026411d52f1",
            "attributes": {
                "changedOn": {
                    "127": "2018-03-07T10:15:40"
                },
                "createdOn": {
                    "127": "2007-12-03T00:00:00"
                },
                "description": {
                    "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>Der Innovations- und Anforderungsprozess gliedert sich in drei Phasen:</p><ul>\n<li>Impulsphase: Beobachtung von Trends, Ideenfindung, Brainstorming von Anforderungen, Kundenanforderungen</li>\n<li>Bewertungsphase: Prüfung auf Tauglichkeit der Idee für das jeweilige Produkt und den Marktanforderungen</li>\n<li>Technologietransfer: Anforderungen in die Release-Planung überführen</li>\n</ul></div>",
                    "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>The Innovation and request process is divided into three phases:</p><ul>\n<li>Pulse phase: review of trends, ideas, brainstorming of requirements, customer requirements</li>\n<li>Evaluation phase: testing for suitability of the idea for the product and market requirements</li>\n<li>Technology transfer: transfer requirements in the release planning</li>\n</ul></div>"
                },
                "name": {
                    "1031": "Ideen/Innovationen",
                    "1033": "Idea/Innovation"
                },
                "processMaturity": {
                    "127": "processIsLived"
                },
                "purp": {
                    "1031": "Qualifizierung eingegangener Ideen und Anforderungen. Unter dem Begriff Qualifizierung versteht man den Vorgang zur Erlangung von Fähigkeiten (Qualifikationen), um eine bestimmte Aufgabe oder Anforderung erfüllen zu können. Ebenso die Überprüfung dieser Fähigkeiten wird als Qualifizierung bezeichnet. Die Überprüfung, dass die Fähigkeiten ausreichen, um im praktischen Einsatz reproduzierbar die gestellten Anforderungen zu erfüllen, ist Inhalt der so genannten Validierung.",
                    "1033": "Qualification of received ideas and requirements. The term qualification is the process of obtaining skills (qualifications), to perform a specific task or requirement can. Similarly, the review of these abilities is called qualification. The verification that the skills sufficient to reproducibly meet the requirements in practical use, is content of the so-called validation."
                },
                "scope": {
                    "1031": "Komplettes Unternehmen",
                    "1033": "Complete company"
                },
                "state1": {
                    "127": "inProcess"
                },
                "validFrom": {
                    "127": "2015-12-01T18:39:48"
                },
                "validFromUntilPastMessage": {
                    "1031": "The date \"01.12.2015\" for \"Gültigkeitsstart\" is in the past.\r\nThe date \"31.03.2016\" for \"Gültigkeitsende\" is in the past.\r\n",
                    "1033": "The date \"12/1/2015\" for \"Start of Validity\" is in the past.\r\nThe date \"3/31/2016\" for \"End of Validity\" is in the past.\r\n"
                },
                "validUntil": {
                    "127": "2016-03-31T00:00:00"
                },
                "workshopImages": {
                    "127": [
                        {
                            "address": "18077efd-e887-4b26-841d-f2374d8da7c1",
                            "fullAddress": "https://demo.symbioworld.com/pz/showcase/Master/editor/1033/BasePlugin/File/GetFile/18077efd-e887-4b26-841d-f2374d8da7c1.Storage.html",
                            "mimeType": "image/jpeg",
                            "protocol": "Storage",
                            "title": "Idea-Innovation_klein"
                        }
                    ]
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
                "changedBy": [
                    {
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "guidelines": [
                    {
                        "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                        "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/0da36332-3ae6-4127-9fb6-6853dbb7245b"
                    },
                    {
                        "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                        "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/c337213a-7585-48a9-9eb2-cff2f9560011"
                    }
                ],
                "hasInput": [
                    {
                        "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                        "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/d23564c5-567b-4439-940e-0efe9b140229"
                    },
                    {
                        "id": "032a3501-4679-4cce-abc6-788394729bf9",
                        "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/3887b540-3670-4f7a-b0b9-c4de9a5e004e"
                    },
                    {
                        "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                        "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/2b251a32-afd8-4140-8406-9bf700189f33"
                    },
                    {
                        "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                        "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/15dcc40d-fb65-494f-9d00-8c537f408347"
                    },
                    {
                        "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                        "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/f6abd383-6a10-4470-b031-99df5748f4d0"
                    }
                ],
                "hasOutput": [
                    {
                        "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                        "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6"
                    },
                    {
                        "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                        "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3"
                    },
                    {
                        "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                        "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b"
                    },
                    {
                        "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                        "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/b5d63e65-6343-42fd-af6f-7d12ee3dc13d"
                    },
                    {
                        "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                        "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/dd5eced4-9771-414f-a8b6-ffd29523d041"
                    },
                    {
                        "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                        "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ac167362-c4c2-4407-a423-00c43e0a7069"
                    }
                ],
                "kpi": [
                    {
                        "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                        "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/657ab3f7-165b-4dc5-9821-52ef417061eb"
                    },
                    {
                        "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                        "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/90955400-f199-11df-2459-ccb6a833f624"
                    }
                ],
                "nonFilteredGuidelines": [
                    {
                        "id": "b794e6f3-f61e-43f1-8e76-865686c81f43",
                        "versionId": "0da36332-3ae6-4127-9fb6-6853dbb7245b",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/0da36332-3ae6-4127-9fb6-6853dbb7245b"
                    },
                    {
                        "id": "d33bdbe6-07c1-47c4-915d-00b02454631f",
                        "versionId": "c337213a-7585-48a9-9eb2-cff2f9560011",
                        "type": "knowledgeStructureDocument",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/KnowledgeStructure/views/PersonalizedArchitecture/elements/c337213a-7585-48a9-9eb2-cff2f9560011"
                    }
                ],
                "nonFilteredHasInput": [
                    {
                        "id": "22fe4a97-1b06-41b8-9e6d-9fe065f8a91d",
                        "versionId": "d23564c5-567b-4439-940e-0efe9b140229",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/d23564c5-567b-4439-940e-0efe9b140229"
                    },
                    {
                        "id": "032a3501-4679-4cce-abc6-788394729bf9",
                        "versionId": "3887b540-3670-4f7a-b0b9-c4de9a5e004e",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/3887b540-3670-4f7a-b0b9-c4de9a5e004e"
                    },
                    {
                        "id": "950f37ab-cb50-4cb9-ba3b-660f9fca8be1",
                        "versionId": "2b251a32-afd8-4140-8406-9bf700189f33",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/2b251a32-afd8-4140-8406-9bf700189f33"
                    },
                    {
                        "id": "b0c55ebe-fa0d-436a-aae7-15d9caa1e741",
                        "versionId": "15dcc40d-fb65-494f-9d00-8c537f408347",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/15dcc40d-fb65-494f-9d00-8c537f408347"
                    },
                    {
                        "id": "554cc9dc-3794-4bf2-992d-98e5ec26b13c",
                        "versionId": "f6abd383-6a10-4470-b031-99df5748f4d0",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/f6abd383-6a10-4470-b031-99df5748f4d0"
                    }
                ],
                "nonFilteredHasOutput": [
                    {
                        "id": "a96a5423-887d-4fd5-bc68-1c4fd339856e",
                        "versionId": "47deb046-fe43-4d1f-a34d-9cbfa75c1fd6",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/47deb046-fe43-4d1f-a34d-9cbfa75c1fd6"
                    },
                    {
                        "id": "70bd7fde-7309-4051-9a17-a9a89d2bf7b9",
                        "versionId": "09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/09a59ddd-3e82-4fdc-a7af-12a5aad0d1e3"
                    },
                    {
                        "id": "36d5f4b4-ca8b-481d-83cc-5c7c780c5018",
                        "versionId": "ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ca7723e3-9c8d-4ac0-b2fd-6c4debe9f41b"
                    },
                    {
                        "id": "980d2829-4479-43c1-8e7d-d91c9a56173b",
                        "versionId": "b5d63e65-6343-42fd-af6f-7d12ee3dc13d",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/b5d63e65-6343-42fd-af6f-7d12ee3dc13d"
                    },
                    {
                        "id": "b1a6b1d1-f732-4aae-bffa-a196854f0aa6",
                        "versionId": "dd5eced4-9771-414f-a8b6-ffd29523d041",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/dd5eced4-9771-414f-a8b6-ffd29523d041"
                    },
                    {
                        "id": "b7e40edb-c364-47b9-aa5c-d0dd054a8138",
                        "versionId": "ac167362-c4c2-4407-a423-00c43e0a7069",
                        "type": "inOut",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/InputsOutputs/views/PersonalizedList/elements/ac167362-c4c2-4407-a423-00c43e0a7069"
                    }
                ],
                "nonFilteredKpi": [
                    {
                        "id": "35274324-e3ad-4bd3-aaa3-543329de231f",
                        "versionId": "657ab3f7-165b-4dc5-9821-52ef417061eb",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/657ab3f7-165b-4dc5-9821-52ef417061eb"
                    },
                    {
                        "id": "6e8d574e-91a4-4ba6-a3fa-ea717b67329c",
                        "versionId": "90955400-f199-11df-2459-ccb6a833f624",
                        "type": "kPI",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/PerformanceIndicators/views/PersonalizedList/elements/90955400-f199-11df-2459-ccb6a833f624"
                    }
                ],
                "nonFilteredRequirements": [
                    {
                        "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                        "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
                    },
                    {
                        "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                        "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
                    }
                ],
                "nonFilteredRisks": [
                    {
                        "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                        "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                        "type": "risk",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/RiskStructure/views/PersonalizedArchitecture/elements/6076b42b-2ff5-4cb6-a353-9e996a368922"
                    }
                ],
                "nonFilteredSecondarySystemsInput": [
                    {
                        "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                        "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/fb925a60-65f7-44de-bef1-e1a23b9cdd4e"
                    }
                ],
                "nonFilteredSecondarySystemsOutput": [
                    {
                        "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                        "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e"
                    },
                    {
                        "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                        "versionId": "ada5da3f-fa08-4944-9c5e-49a52a7f86dc",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/ada5da3f-fa08-4944-9c5e-49a52a7f86dc"
                    }
                ],
                "nonFilteredSystems": [
                    {
                        "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                        "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a"
                    }
                ],
                "nonFilteredTrainings": [
                    {
                        "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                        "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                        "type": "training",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Trainings/views/PersonalizedList/elements/aa346082-cfc1-4695-accc-a1673947987b"
                    }
                ],
                "organisations": [
                    {
                        "id": "43320ec1-1d8b-46b8-93e1-037a2d61d208",
                        "versionId": "171fe695-8776-49fc-9fda-ac37a1728299",
                        "type": "orgUnit",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Organization/views/Architecture/elements/171fe695-8776-49fc-9fda-ac37a1728299"
                    }
                ],
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "qualityManager": [
                    {
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ],
                "releaseHistory": [
                    {
                        "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
                        "versionId": "9fe36070-f0c0-11df-4e21-001c25729284",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/9fe36070-f0c0-11df-4e21-001c25729284"
                    }
                ],
                "requirements": [
                    {
                        "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                        "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
                    },
                    {
                        "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                        "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
                    }
                ],
                "risks": [
                    {
                        "id": "f23da386-726b-4938-b5c4-a7603a6c9e0b",
                        "versionId": "6076b42b-2ff5-4cb6-a353-9e996a368922",
                        "type": "risk",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/RiskStructure/views/PersonalizedArchitecture/elements/6076b42b-2ff5-4cb6-a353-9e996a368922"
                    }
                ],
                "secondarySystemsInput": [
                    {
                        "id": "732e54f3-063d-497b-9ec3-7e441eb3d531",
                        "versionId": "fb925a60-65f7-44de-bef1-e1a23b9cdd4e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/fb925a60-65f7-44de-bef1-e1a23b9cdd4e"
                    }
                ],
                "secondarySystemsOutput": [
                    {
                        "id": "a036f63f-7797-40fa-8639-503bfe4d4449",
                        "versionId": "03fb3d51-7ce8-4fbe-8b67-fe192d6db48e",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/03fb3d51-7ce8-4fbe-8b67-fe192d6db48e"
                    },
                    {
                        "id": "1f66af8a-6291-4d58-91c4-5c7c61b57995",
                        "versionId": "ada5da3f-fa08-4944-9c5e-49a52a7f86dc",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/ada5da3f-fa08-4944-9c5e-49a52a7f86dc"
                    }
                ],
                "systems": [
                    {
                        "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
                        "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
                        "type": "system",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/ITArchitecture/views/PersonalizedArchitecture/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a"
                    }
                ],
                "trainings": [
                    {
                        "id": "83d40a36-bcd8-4702-b4ea-8c90ae792632",
                        "versionId": "aa346082-cfc1-4695-accc-a1673947987b",
                        "type": "training",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Trainings/views/PersonalizedList/elements/aa346082-cfc1-4695-accc-a1673947987b"
                    }
                ]
            }
        }
    ]
}
```

### Get a specific element from the *detail* view of the *processes* facet and only include the attributes *name* and *author*

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/168c8bc4-779e-4697-8334-0026411d52f1?$select=name,author
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "168c8bc4-779e-4697-8334-0026411d52f1",
            "attributes": {
                "name": {
                    "1031": "Ideen/Innovationen",
                    "1033": "Idea/Innovation"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Users/views/List/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ]
            },
            "content": [
                {
                    "id": "6ba15f74-9fad-4cbd-b51d-eb09255f9125",
                    "type": "func"
                },
                {
                    "id": "d567a583-6240-4e53-a8ab-6edc14482019",
                    "type": "ruleAnd"
                },
                {
                    "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                    "versionId": "664fd624-d341-4521-b430-897bb16399f4",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/664fd624-d341-4521-b430-897bb16399f4"
                },
                {
                    "id": "173f80e7-1b7f-4c4b-9266-ea8177c33267",
                    "type": "func"
                },
                {
                    "id": "8824f210-f0cf-4348-8bf9-3f3a1b7ade62",
                    "type": "func"
                },
                {
                    "id": "c8cc7945-2f18-4bda-b53c-934e0f29a17b",
                    "type": "func"
                },
                {
                    "id": "2c3abe5c-6c1f-4e3f-9db6-5fcda2ffeef1",
                    "type": "func"
                },
                {
                    "id": "850b13ec-a5cd-4d41-9ea1-7a508861d2b8",
                    "type": "evStart"
                },
                {
                    "id": "50f66862-90cb-42c6-9ccb-5a186f4c5259",
                    "type": "funcCondition"
                },
                {
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                {
                    "id": "e1cc7546-41de-40c9-9ebf-db3f8440de4f",
                    "type": "ruleAnd"
                },
                {
                    "id": "96ad0409-9018-4ebe-9bc2-8b1ba4edf7ef",
                    "type": "funcCondition"
                },
                {
                    "id": "731d1fb1-4e7b-4a51-8af1-58914db6f50b",
                    "type": "funcCondition"
                },
                {
                    "id": "1282b5f8-fd30-4e89-8d26-b7323b78d76d",
                    "type": "evIntermediate"
                },
                {
                    "id": "aefa209f-38d4-4895-abe7-f779b555c6ed",
                    "type": "ruleXor"
                },
                {
                    "id": "2c3601d2-aeb2-4c66-a936-1a8f660b1723",
                    "type": "ruleXor"
                },
                {
                    "id": "b80379bc-137e-40f7-a95e-3d5f4ec39aa4",
                    "type": "func"
                },
                {
                    "id": "3e8d271e-8538-46c3-a7d2-c40d90e588d4",
                    "type": "funcCondition"
                },
                {
                    "id": "070269f5-7b41-4d09-94ca-4b88fa518a32",
                    "type": "func"
                },
                {
                    "id": "07b12234-3eb1-4cdb-8973-26a0135b6549",
                    "type": "func"
                },
                {
                    "id": "a201a5cb-8ab9-4d6d-a5d6-f070b1922c17",
                    "type": "ruleXor"
                },
                {
                    "id": "fc2e9a36-239a-40e4-8caf-666f32e8ea9a",
                    "type": "func"
                },
                {
                    "id": "83adec24-87dc-4a42-b2b5-9025c704c0f6",
                    "type": "evEnd"
                },
                {
                    "id": "f2adfa58-3efc-4577-8d1c-0a787a6e947a",
                    "type": "func"
                },
                {
                    "id": "ceda130c-e979-4d2b-ac1f-1718c6e2e389",
                    "type": "funcCondition"
                },
                {
                    "id": "baf01625-3395-49cf-adbe-9ec4efcd18fe",
                    "type": "func"
                },
                {
                    "id": "5e625082-ffc0-43d5-843e-547f64fd447a",
                    "type": "func"
                },
                {
                    "id": "7fdd1a63-bcd5-414f-b16c-dce08a8328b8",
                    "type": "evEnd"
                }
            ]
        }
    ]
}
```

### Get a specific element from the *detail* view of the *processes* facet and only include and expand the *requirements*

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/168c8bc4-779e-4697-8334-0026411d52f1?$select=requirements&$expandRelated=requirements
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "168c8bc4-779e-4697-8334-0026411d52f1",
            "related": {
                "requirements": [
                    {
                        "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                        "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/1d5545cd-7d23-4d96-b89b-e44bf176623e"
                    },
                    {
                        "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                        "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                        "type": "requirement",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Requirements/views/PersonalizedArchitecture/elements/414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b"
                    }
                ]
            },
            "content": [
                {
                    "id": "6ba15f74-9fad-4cbd-b51d-eb09255f9125",
                    "type": "func"
                },
                {
                    "id": "d567a583-6240-4e53-a8ab-6edc14482019",
                    "type": "ruleAnd"
                },
                {
                    "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                    "versionId": "664fd624-d341-4521-b430-897bb16399f4",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/664fd624-d341-4521-b430-897bb16399f4"
                },
                {
                    "id": "173f80e7-1b7f-4c4b-9266-ea8177c33267",
                    "type": "func"
                },
                {
                    "id": "8824f210-f0cf-4348-8bf9-3f3a1b7ade62",
                    "type": "func"
                },
                {
                    "id": "c8cc7945-2f18-4bda-b53c-934e0f29a17b",
                    "type": "func"
                },
                {
                    "id": "2c3abe5c-6c1f-4e3f-9db6-5fcda2ffeef1",
                    "type": "func"
                },
                {
                    "id": "850b13ec-a5cd-4d41-9ea1-7a508861d2b8",
                    "type": "evStart"
                },
                {
                    "id": "50f66862-90cb-42c6-9ccb-5a186f4c5259",
                    "type": "funcCondition"
                },
                {
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/Processes/views/TreeAndDiagram/elements/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                {
                    "id": "e1cc7546-41de-40c9-9ebf-db3f8440de4f",
                    "type": "ruleAnd"
                },
                {
                    "id": "96ad0409-9018-4ebe-9bc2-8b1ba4edf7ef",
                    "type": "funcCondition"
                },
                {
                    "id": "731d1fb1-4e7b-4a51-8af1-58914db6f50b",
                    "type": "funcCondition"
                },
                {
                    "id": "1282b5f8-fd30-4e89-8d26-b7323b78d76d",
                    "type": "evIntermediate"
                },
                {
                    "id": "aefa209f-38d4-4895-abe7-f779b555c6ed",
                    "type": "ruleXor"
                },
                {
                    "id": "2c3601d2-aeb2-4c66-a936-1a8f660b1723",
                    "type": "ruleXor"
                },
                {
                    "id": "b80379bc-137e-40f7-a95e-3d5f4ec39aa4",
                    "type": "func"
                },
                {
                    "id": "3e8d271e-8538-46c3-a7d2-c40d90e588d4",
                    "type": "funcCondition"
                },
                {
                    "id": "070269f5-7b41-4d09-94ca-4b88fa518a32",
                    "type": "func"
                },
                {
                    "id": "07b12234-3eb1-4cdb-8973-26a0135b6549",
                    "type": "func"
                },
                {
                    "id": "a201a5cb-8ab9-4d6d-a5d6-f070b1922c17",
                    "type": "ruleXor"
                },
                {
                    "id": "fc2e9a36-239a-40e4-8caf-666f32e8ea9a",
                    "type": "func"
                },
                {
                    "id": "83adec24-87dc-4a42-b2b5-9025c704c0f6",
                    "type": "evEnd"
                },
                {
                    "id": "f2adfa58-3efc-4577-8d1c-0a787a6e947a",
                    "type": "func"
                },
                {
                    "id": "ceda130c-e979-4d2b-ac1f-1718c6e2e389",
                    "type": "funcCondition"
                },
                {
                    "id": "baf01625-3395-49cf-adbe-9ec4efcd18fe",
                    "type": "func"
                },
                {
                    "id": "5e625082-ffc0-43d5-843e-547f64fd447a",
                    "type": "func"
                },
                {
                    "id": "7fdd1a63-bcd5-414f-b16c-dce08a8328b8",
                    "type": "evEnd"
                }
            ]
        }
    ]
```

### Get a the root path elements of a specific element from the *tree* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/cd5e6ffa-53fd-4167-97e0-a7f9a974d00a?$resources=rootPath
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "662130a1-43bc-413c-a2da-82b988d7f2dc",
            "versionId": "cd5e6ffa-53fd-4167-97e0-a7f9a974d00a",
            "creationId": "0d5d1c4f-4a96-442a-83a0-8f530f3a214f",
            "type": "subProcess",
            "state": "released",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/cd5e6ffa-53fd-4167-97e0-a7f9a974d00a",
            "rootPath": [
                {
                    "id": "03939019-1db0-4a3c-87fb-14eabb4afd91",
                    "versionId": "d75736c4-850c-4253-a72b-fbc2c5633745",
                    "creationId": "8eede6cd-0ee5-4a2b-9cf0-4e976fffd5df",
                    "type": "subProcess",
                    "state": "released",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/d75736c4-850c-4253-a72b-fbc2c5633745"
                },
                {
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
                    "type": "processHouse",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/ab2835f8-da30-4e36-a863-456e1105bb58"
                }
            ]
        }
    ]
}
```

### Get the stereotype element of a specific element from the *tree* view of the *it* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/tree/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a?$resources=stereotype
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
            "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
            "type": "system",
            "state": "released",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/detail/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
            "stereotype": {
                "id": "48e09f27-e392-4b25-b335-9eefb5410af0",
                "creationId": "48e09f27-e392-4b25-b335-9eefb5410af0",
                "type": "systemType",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/stereotypes/views/detail/elements/48e09f27-e392-4b25-b335-9eefb5410af0"
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
