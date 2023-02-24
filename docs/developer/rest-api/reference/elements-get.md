# Elements get

**api-version**: 4.0

Retrieves a specific element.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}
```

With optional parameters

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}?$filter={filter}&$select={select}&$expandRelated={expand}
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
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |
| $resources | query | | string ["attributes", "related", "children", "content", "displayNames", "rootPath"] | The resources to include. If not specified all resources will be included. |
| $select | query | | string | A comma separated list of namesof the attributes/related contexts to include. |
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |

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

### Get a specific element from the *detail* view of the *processes* facet

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/a2d5b2ae-8c41-424f-aca1-9710b3d9f2bf
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "25d30f88-323f-4320-8b6e-75169e5ce07f",
            "versionId": "a2d5b2ae-8c41-424f-aca1-9710b3d9f2bf",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-04-06T11:40:58"
                },
                "createdOn": {
                    "127": "2015-11-27T18:04:59"
                },
                "description": {
                    "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>Bei einem Wareneingang zu einer Bestellung schlägt das System die noch offene Bestellmenge einer Position für den Wareneingang vor. Diese Menge kann geändert werden, falls die gelieferte Menge abweicht. Die gelieferte Menge wird mit der offenen Bestellmenge verglichen. Dadurch kann gleich eine Unter- oder Überlieferung festgestellt werden.</p>",
                    "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>During a goods receipt for a purchase order, the system proposes the outstanding order quantity of an item for the goods receipt. This amount can be changed, if the quantity delivered differs. The quantity delivered is compared with the open order quantity. As a result, an under or over delivery can be detected.</p>"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/a2d5b2ae-8c41-424f-aca1-9710b3d9f2bf",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/a2d5b2ae-8c41-424f-aca1-9710b3d9f2bf"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Unter-/Überlieferungs-\nProzess",
                    "1033": "Under/over \ndelivery process"
                },
                "state1": {
                    "127": "inProcess"
                },
                "validUntil": {
                    "127": "9999-12-31T00:00:00"
                },
                "version": {
                    "127": "0.1"
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
                "createdBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "organizationFilters": [
                    {
                        "facetName": "organization",
                        "id": "bef7c369-b963-4d7f-a45d-24b61e476b42",
                        "versionId": "a1a08cbc-1455-427a-bf4a-d59871fa8bc2",
                        "type": "orgUnit",
                        "state": "inEffect",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/organization/views/detail/elements/a1a08cbc-1455-427a-bf4a-d59871fa8bc2",
                        "stereotype": "division"
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
                ],
                "qualityManager": [
                    {
                        "facetName": "users",
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ]
            }
        }
    ]
}
```

### Get a specific element from the *detail* view of the *processes* facet with the resources *attributes* and *related*

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-10-03T15:34:19"
                },
                "createdOn": {
                    "127": "2018-10-03T15:34:11"
                },
                "description": {
                    "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>Der Innovations- und Anforderungsprozess gliedert sich in drei Phasen:</p><ul>\n<li>Impulsphase: Beobachtung von Trends, Ideenfindung, Brainstorming von Anforderungen, Kundenanforderungen</li>\n<li>Bewertungsphase: Prüfung auf Tauglichkeit der Idee für das jeweilige Produkt und den Marktanforderungen</li>\n<li>Technologietransfer: Anforderungen in die Release-Planung überführen</li>\n</ul></div>",
                    "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>The Innovation and request process is divided into three phases:</p><ul>\n<li>Pulse phase: review of trends, ideas, brainstorming of requirements, customer requirements</li>\n<li>Evaluation phase: testing for suitability of the idea for the product and market requirements</li>\n<li>Technology transfer: transfer requirements in the release planning</li>\n</ul></div>"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Ideen/Innovationen",
                    "1033": "Idea/Innovation"
                },
                "processMaturity": {
                    "127": "isLived"
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
                "validUntil": {
                    "127": "2019-10-03T00:00:00"
                },
                "version": {
                    "127": "2.1"
                },
                "workshopImages": {
                    "127": [
                        {
                            "address": "18077efd-e887-4b26-841d-f2374d8da7c1",
                            "fullAddress": "https://demo.symbioworld.com/pz/showcase/editor/1033/BasePlugin/File/GetFile/18077efd-e887-4b26-841d-f2374d8da7c1.Storage.html",
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
            },
            "content": [
                {
                    "facetName": "processes",
                    "id": "4b0baa9a-d194-476f-adcd-873061a0aab5",
                    "creationId": "07b12234-3eb1-4cdb-8973-26a0135b6549",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/4b0baa9a-d194-476f-adcd-873061a0aab5"
                },
                {
                    "facetName": "processes",
                    "id": "2e39b478-3404-4370-a42b-9f5132ed716f",
                    "creationId": "aefa209f-38d4-4895-abe7-f779b555c6ed",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2e39b478-3404-4370-a42b-9f5132ed716f"
                },
                {
                    "facetName": "processes",
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "type": "subProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                {
                    "facetName": "processes",
                    "id": "8a189545-b520-4f4d-b031-ca17fecd0e55",
                    "creationId": "1282b5f8-fd30-4e89-8d26-b7323b78d76d",
                    "type": "evIntermediate",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a189545-b520-4f4d-b031-ca17fecd0e55"
                },
                {
                    "facetName": "processes",
                    "id": "6672ba3c-afd8-4125-b619-cac51a6bdd31",
                    "creationId": "baf01625-3395-49cf-adbe-9ec4efcd18fe",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6672ba3c-afd8-4125-b619-cac51a6bdd31"
                },
                {
                    "facetName": "processes",
                    "id": "bcb25116-a8a2-4ba0-8dd4-1ff2789aac01",
                    "creationId": "fc2e9a36-239a-40e4-8caf-666f32e8ea9a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/bcb25116-a8a2-4ba0-8dd4-1ff2789aac01"
                },
                {
                    "facetName": "processes",
                    "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                    "versionId": "664fd624-d341-4521-b430-897bb16399f4",
                    "type": "subProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/664fd624-d341-4521-b430-897bb16399f4"
                },
                {
                    "facetName": "processes",
                    "id": "218c8a5a-4716-4b9f-a985-44faf3a94ac3",
                    "creationId": "6ba15f74-9fad-4cbd-b51d-eb09255f9125",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/218c8a5a-4716-4b9f-a985-44faf3a94ac3"
                },
                {
                    "facetName": "processes",
                    "id": "c7fc4a2e-33d5-43ba-864d-23e050fe5056",
                    "creationId": "e1cc7546-41de-40c9-9ebf-db3f8440de4f",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c7fc4a2e-33d5-43ba-864d-23e050fe5056"
                },
                {
                    "facetName": "processes",
                    "id": "60b9fd06-7827-4944-af8b-c2a3811c2d67",
                    "creationId": "2c3601d2-aeb2-4c66-a936-1a8f660b1723",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/60b9fd06-7827-4944-af8b-c2a3811c2d67"
                },
                {
                    "facetName": "processes",
                    "id": "9bd738b0-a212-4a5b-9d41-3cfca0f06ed0",
                    "creationId": "a201a5cb-8ab9-4d6d-a5d6-f070b1922c17",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9bd738b0-a212-4a5b-9d41-3cfca0f06ed0"
                },
                {
                    "facetName": "processes",
                    "id": "ca4b3d85-b13d-481c-9ffe-f1c127e7ea86",
                    "creationId": "7fdd1a63-bcd5-414f-b16c-dce08a8328b8",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ca4b3d85-b13d-481c-9ffe-f1c127e7ea86"
                },
                {
                    "facetName": "processes",
                    "id": "2c110fd4-6548-4fe1-83d5-a3c7613cc880",
                    "creationId": "850b13ec-a5cd-4d41-9ea1-7a508861d2b8",
                    "type": "evStart",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2c110fd4-6548-4fe1-83d5-a3c7613cc880"
                },
                {
                    "facetName": "processes",
                    "id": "c471ddc0-b4b5-4621-96bd-1e45aa258e3c",
                    "creationId": "c8cc7945-2f18-4bda-b53c-934e0f29a17b",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c471ddc0-b4b5-4621-96bd-1e45aa258e3c"
                },
                {
                    "facetName": "processes",
                    "id": "7a17b1c9-b4b9-4bb7-a705-154469ff6329",
                    "creationId": "83adec24-87dc-4a42-b2b5-9025c704c0f6",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/7a17b1c9-b4b9-4bb7-a705-154469ff6329"
                },
                {
                    "facetName": "processes",
                    "id": "30d9728c-83a1-4a68-9e67-49b0b35b828c",
                    "creationId": "d567a583-6240-4e53-a8ab-6edc14482019",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/30d9728c-83a1-4a68-9e67-49b0b35b828c"
                },
                {
                    "facetName": "processes",
                    "id": "ffbcab0b-2521-44c5-9ccd-d1d9f4b0f2e7",
                    "creationId": "ceda130c-e979-4d2b-ac1f-1718c6e2e389",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ffbcab0b-2521-44c5-9ccd-d1d9f4b0f2e7"
                },
                {
                    "facetName": "processes",
                    "id": "75581a9f-09b5-4065-8ec2-7571c86c27de",
                    "creationId": "3e8d271e-8538-46c3-a7d2-c40d90e588d4",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/75581a9f-09b5-4065-8ec2-7571c86c27de"
                },
                {
                    "facetName": "processes",
                    "id": "7ee09460-df33-4f0d-bf6d-2ebff2c6c868",
                    "creationId": "96ad0409-9018-4ebe-9bc2-8b1ba4edf7ef",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/7ee09460-df33-4f0d-bf6d-2ebff2c6c868"
                },
                {
                    "facetName": "processes",
                    "id": "16909c29-4da3-4bbf-a721-6a2cb721efb7",
                    "creationId": "5e625082-ffc0-43d5-843e-547f64fd447a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/16909c29-4da3-4bbf-a721-6a2cb721efb7"
                },
                {
                    "facetName": "processes",
                    "id": "539dfff6-7aa7-45e0-a5c9-8f2af30885af",
                    "creationId": "f2adfa58-3efc-4577-8d1c-0a787a6e947a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/539dfff6-7aa7-45e0-a5c9-8f2af30885af"
                },
                {
                    "facetName": "processes",
                    "id": "c18b13a7-c0a8-4010-a6b9-30f1f503232b",
                    "creationId": "50f66862-90cb-42c6-9ccb-5a186f4c5259",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c18b13a7-c0a8-4010-a6b9-30f1f503232b"
                },
                {
                    "facetName": "processes",
                    "id": "c7aa00d0-7d2f-47d8-ad3e-e108aaa30047",
                    "creationId": "2c3abe5c-6c1f-4e3f-9db6-5fcda2ffeef1",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c7aa00d0-7d2f-47d8-ad3e-e108aaa30047"
                },
                {
                    "facetName": "processes",
                    "id": "4e56a725-71ef-466b-94d3-1a032eb0730b",
                    "creationId": "731d1fb1-4e7b-4a51-8af1-58914db6f50b",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/4e56a725-71ef-466b-94d3-1a032eb0730b"
                },
                {
                    "facetName": "processes",
                    "id": "db214c33-e2da-45cb-8bb1-7405dafe711f",
                    "creationId": "070269f5-7b41-4d09-94ca-4b88fa518a32",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/db214c33-e2da-45cb-8bb1-7405dafe711f"
                }
            ]
        }
    ]
}
```

### Get a specific element from the *detail* view of the *processes* facet and only include the attributes *name* and *author*

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5?$select=name,author
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "name": {
                    "1031": "Ideen/Innovationen",
                    "1033": "Idea/Innovation"
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
                ]
            },
            "content": [
                {
                    "facetName": "processes",
                    "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                    "versionId": "664fd624-d341-4521-b430-897bb16399f4",
                    "type": "subProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/664fd624-d341-4521-b430-897bb16399f4"
                },
                {
                    "facetName": "processes",
                    "id": "c7aa00d0-7d2f-47d8-ad3e-e108aaa30047",
                    "creationId": "2c3abe5c-6c1f-4e3f-9db6-5fcda2ffeef1",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c7aa00d0-7d2f-47d8-ad3e-e108aaa30047"
                },
                {
                    "facetName": "processes",
                    "id": "9bd738b0-a212-4a5b-9d41-3cfca0f06ed0",
                    "creationId": "a201a5cb-8ab9-4d6d-a5d6-f070b1922c17",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9bd738b0-a212-4a5b-9d41-3cfca0f06ed0"
                },
                {
                    "facetName": "processes",
                    "id": "ffbcab0b-2521-44c5-9ccd-d1d9f4b0f2e7",
                    "creationId": "ceda130c-e979-4d2b-ac1f-1718c6e2e389",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ffbcab0b-2521-44c5-9ccd-d1d9f4b0f2e7"
                },
                {
                    "facetName": "processes",
                    "id": "c7fc4a2e-33d5-43ba-864d-23e050fe5056",
                    "creationId": "e1cc7546-41de-40c9-9ebf-db3f8440de4f",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c7fc4a2e-33d5-43ba-864d-23e050fe5056"
                },
                {
                    "facetName": "processes",
                    "id": "539dfff6-7aa7-45e0-a5c9-8f2af30885af",
                    "creationId": "f2adfa58-3efc-4577-8d1c-0a787a6e947a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/539dfff6-7aa7-45e0-a5c9-8f2af30885af"
                },
                {
                    "facetName": "processes",
                    "id": "30d9728c-83a1-4a68-9e67-49b0b35b828c",
                    "creationId": "d567a583-6240-4e53-a8ab-6edc14482019",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/30d9728c-83a1-4a68-9e67-49b0b35b828c"
                },
                {
                    "facetName": "processes",
                    "id": "4e56a725-71ef-466b-94d3-1a032eb0730b",
                    "creationId": "731d1fb1-4e7b-4a51-8af1-58914db6f50b",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/4e56a725-71ef-466b-94d3-1a032eb0730b"
                },
                {
                    "facetName": "processes",
                    "id": "8a189545-b520-4f4d-b031-ca17fecd0e55",
                    "creationId": "1282b5f8-fd30-4e89-8d26-b7323b78d76d",
                    "type": "evIntermediate",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a189545-b520-4f4d-b031-ca17fecd0e55"
                },
                {
                    "facetName": "processes",
                    "id": "7ee09460-df33-4f0d-bf6d-2ebff2c6c868",
                    "creationId": "96ad0409-9018-4ebe-9bc2-8b1ba4edf7ef",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/7ee09460-df33-4f0d-bf6d-2ebff2c6c868"
                },
                {
                    "facetName": "processes",
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "type": "subProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                {
                    "facetName": "processes",
                    "id": "60b9fd06-7827-4944-af8b-c2a3811c2d67",
                    "creationId": "2c3601d2-aeb2-4c66-a936-1a8f660b1723",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/60b9fd06-7827-4944-af8b-c2a3811c2d67"
                },
                {
                    "facetName": "processes",
                    "id": "c471ddc0-b4b5-4621-96bd-1e45aa258e3c",
                    "creationId": "c8cc7945-2f18-4bda-b53c-934e0f29a17b",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c471ddc0-b4b5-4621-96bd-1e45aa258e3c"
                },
                {
                    "facetName": "processes",
                    "id": "7a17b1c9-b4b9-4bb7-a705-154469ff6329",
                    "creationId": "83adec24-87dc-4a42-b2b5-9025c704c0f6",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/7a17b1c9-b4b9-4bb7-a705-154469ff6329"
                },
                {
                    "facetName": "processes",
                    "id": "ca4b3d85-b13d-481c-9ffe-f1c127e7ea86",
                    "creationId": "7fdd1a63-bcd5-414f-b16c-dce08a8328b8",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ca4b3d85-b13d-481c-9ffe-f1c127e7ea86"
                },
                {
                    "facetName": "processes",
                    "id": "4b0baa9a-d194-476f-adcd-873061a0aab5",
                    "creationId": "07b12234-3eb1-4cdb-8973-26a0135b6549",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/4b0baa9a-d194-476f-adcd-873061a0aab5"
                },
                {
                    "facetName": "processes",
                    "id": "6672ba3c-afd8-4125-b619-cac51a6bdd31",
                    "creationId": "baf01625-3395-49cf-adbe-9ec4efcd18fe",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6672ba3c-afd8-4125-b619-cac51a6bdd31"
                },
                {
                    "facetName": "processes",
                    "id": "c18b13a7-c0a8-4010-a6b9-30f1f503232b",
                    "creationId": "50f66862-90cb-42c6-9ccb-5a186f4c5259",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c18b13a7-c0a8-4010-a6b9-30f1f503232b"
                },
                {
                    "facetName": "processes",
                    "id": "db214c33-e2da-45cb-8bb1-7405dafe711f",
                    "creationId": "070269f5-7b41-4d09-94ca-4b88fa518a32",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/db214c33-e2da-45cb-8bb1-7405dafe711f"
                },
                {
                    "facetName": "processes",
                    "id": "2c110fd4-6548-4fe1-83d5-a3c7613cc880",
                    "creationId": "850b13ec-a5cd-4d41-9ea1-7a508861d2b8",
                    "type": "evStart",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2c110fd4-6548-4fe1-83d5-a3c7613cc880"
                },
                {
                    "facetName": "processes",
                    "id": "75581a9f-09b5-4065-8ec2-7571c86c27de",
                    "creationId": "3e8d271e-8538-46c3-a7d2-c40d90e588d4",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/75581a9f-09b5-4065-8ec2-7571c86c27de"
                },
                {
                    "facetName": "processes",
                    "id": "bcb25116-a8a2-4ba0-8dd4-1ff2789aac01",
                    "creationId": "fc2e9a36-239a-40e4-8caf-666f32e8ea9a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/bcb25116-a8a2-4ba0-8dd4-1ff2789aac01"
                },
                {
                    "facetName": "processes",
                    "id": "2e39b478-3404-4370-a42b-9f5132ed716f",
                    "creationId": "aefa209f-38d4-4895-abe7-f779b555c6ed",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2e39b478-3404-4370-a42b-9f5132ed716f"
                },
                {
                    "facetName": "processes",
                    "id": "16909c29-4da3-4bbf-a721-6a2cb721efb7",
                    "creationId": "5e625082-ffc0-43d5-843e-547f64fd447a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/16909c29-4da3-4bbf-a721-6a2cb721efb7"
                },
                {
                    "facetName": "processes",
                    "id": "218c8a5a-4716-4b9f-a985-44faf3a94ac3",
                    "creationId": "6ba15f74-9fad-4cbd-b51d-eb09255f9125",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/218c8a5a-4716-4b9f-a985-44faf3a94ac3"
                }
            ]
        }
    ]
}
```

### Get a specific element from the *detail* view of the *processes* facet and only include and expand the *requirements*

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5?$select=requirements&$expandRelated=requirements
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "related": {
                "requirements": [
                    {
                        "facetName": "requirements",
                        "id": "19b1188a-6cf8-465b-acc1-1e9134a20b77",
                        "versionId": "414e448d-6e0e-4db2-9c7f-7c3e3fd37b0b",
                        "type": "requirement",
                        "state": "inEffect"
                    },
                    {
                        "facetName": "requirements",
                        "id": "199c6546-fd51-40b6-a76b-1bbca4cd2bed",
                        "versionId": "1d5545cd-7d23-4d96-b89b-e44bf176623e",
                        "type": "requirement",
                        "state": "inEffect"
                    }
                ]
            },
            "content": [
                {
                    "facetName": "processes",
                    "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                    "versionId": "664fd624-d341-4521-b430-897bb16399f4",
                    "type": "subProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/664fd624-d341-4521-b430-897bb16399f4"
                },
                {
                    "facetName": "processes",
                    "id": "c7aa00d0-7d2f-47d8-ad3e-e108aaa30047",
                    "creationId": "2c3abe5c-6c1f-4e3f-9db6-5fcda2ffeef1",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c7aa00d0-7d2f-47d8-ad3e-e108aaa30047"
                },
                {
                    "facetName": "processes",
                    "id": "9bd738b0-a212-4a5b-9d41-3cfca0f06ed0",
                    "creationId": "a201a5cb-8ab9-4d6d-a5d6-f070b1922c17",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9bd738b0-a212-4a5b-9d41-3cfca0f06ed0"
                },
                {
                    "facetName": "processes",
                    "id": "ffbcab0b-2521-44c5-9ccd-d1d9f4b0f2e7",
                    "creationId": "ceda130c-e979-4d2b-ac1f-1718c6e2e389",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ffbcab0b-2521-44c5-9ccd-d1d9f4b0f2e7"
                },
                {
                    "facetName": "processes",
                    "id": "c7fc4a2e-33d5-43ba-864d-23e050fe5056",
                    "creationId": "e1cc7546-41de-40c9-9ebf-db3f8440de4f",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c7fc4a2e-33d5-43ba-864d-23e050fe5056"
                },
                {
                    "facetName": "processes",
                    "id": "539dfff6-7aa7-45e0-a5c9-8f2af30885af",
                    "creationId": "f2adfa58-3efc-4577-8d1c-0a787a6e947a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/539dfff6-7aa7-45e0-a5c9-8f2af30885af"
                },
                {
                    "facetName": "processes",
                    "id": "30d9728c-83a1-4a68-9e67-49b0b35b828c",
                    "creationId": "d567a583-6240-4e53-a8ab-6edc14482019",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/30d9728c-83a1-4a68-9e67-49b0b35b828c"
                },
                {
                    "facetName": "processes",
                    "id": "4e56a725-71ef-466b-94d3-1a032eb0730b",
                    "creationId": "731d1fb1-4e7b-4a51-8af1-58914db6f50b",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/4e56a725-71ef-466b-94d3-1a032eb0730b"
                },
                {
                    "facetName": "processes",
                    "id": "8a189545-b520-4f4d-b031-ca17fecd0e55",
                    "creationId": "1282b5f8-fd30-4e89-8d26-b7323b78d76d",
                    "type": "evIntermediate",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a189545-b520-4f4d-b031-ca17fecd0e55"
                },
                {
                    "facetName": "processes",
                    "id": "7ee09460-df33-4f0d-bf6d-2ebff2c6c868",
                    "creationId": "96ad0409-9018-4ebe-9bc2-8b1ba4edf7ef",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/7ee09460-df33-4f0d-bf6d-2ebff2c6c868"
                },
                {
                    "facetName": "processes",
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "type": "subProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                {
                    "facetName": "processes",
                    "id": "60b9fd06-7827-4944-af8b-c2a3811c2d67",
                    "creationId": "2c3601d2-aeb2-4c66-a936-1a8f660b1723",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/60b9fd06-7827-4944-af8b-c2a3811c2d67"
                },
                {
                    "facetName": "processes",
                    "id": "c471ddc0-b4b5-4621-96bd-1e45aa258e3c",
                    "creationId": "c8cc7945-2f18-4bda-b53c-934e0f29a17b",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c471ddc0-b4b5-4621-96bd-1e45aa258e3c"
                },
                {
                    "facetName": "processes",
                    "id": "7a17b1c9-b4b9-4bb7-a705-154469ff6329",
                    "creationId": "83adec24-87dc-4a42-b2b5-9025c704c0f6",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/7a17b1c9-b4b9-4bb7-a705-154469ff6329"
                },
                {
                    "facetName": "processes",
                    "id": "ca4b3d85-b13d-481c-9ffe-f1c127e7ea86",
                    "creationId": "7fdd1a63-bcd5-414f-b16c-dce08a8328b8",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ca4b3d85-b13d-481c-9ffe-f1c127e7ea86"
                },
                {
                    "facetName": "processes",
                    "id": "4b0baa9a-d194-476f-adcd-873061a0aab5",
                    "creationId": "07b12234-3eb1-4cdb-8973-26a0135b6549",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/4b0baa9a-d194-476f-adcd-873061a0aab5"
                },
                {
                    "facetName": "processes",
                    "id": "6672ba3c-afd8-4125-b619-cac51a6bdd31",
                    "creationId": "baf01625-3395-49cf-adbe-9ec4efcd18fe",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/6672ba3c-afd8-4125-b619-cac51a6bdd31"
                },
                {
                    "facetName": "processes",
                    "id": "c18b13a7-c0a8-4010-a6b9-30f1f503232b",
                    "creationId": "50f66862-90cb-42c6-9ccb-5a186f4c5259",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c18b13a7-c0a8-4010-a6b9-30f1f503232b"
                },
                {
                    "facetName": "processes",
                    "id": "db214c33-e2da-45cb-8bb1-7405dafe711f",
                    "creationId": "070269f5-7b41-4d09-94ca-4b88fa518a32",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/db214c33-e2da-45cb-8bb1-7405dafe711f"
                },
                {
                    "facetName": "processes",
                    "id": "2c110fd4-6548-4fe1-83d5-a3c7613cc880",
                    "creationId": "850b13ec-a5cd-4d41-9ea1-7a508861d2b8",
                    "type": "evStart",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2c110fd4-6548-4fe1-83d5-a3c7613cc880"
                },
                {
                    "facetName": "processes",
                    "id": "75581a9f-09b5-4065-8ec2-7571c86c27de",
                    "creationId": "3e8d271e-8538-46c3-a7d2-c40d90e588d4",
                    "type": "condition",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/75581a9f-09b5-4065-8ec2-7571c86c27de"
                },
                {
                    "facetName": "processes",
                    "id": "bcb25116-a8a2-4ba0-8dd4-1ff2789aac01",
                    "creationId": "fc2e9a36-239a-40e4-8caf-666f32e8ea9a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/bcb25116-a8a2-4ba0-8dd4-1ff2789aac01"
                },
                {
                    "facetName": "processes",
                    "id": "2e39b478-3404-4370-a42b-9f5132ed716f",
                    "creationId": "aefa209f-38d4-4895-abe7-f779b555c6ed",
                    "type": "ruleXor",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/2e39b478-3404-4370-a42b-9f5132ed716f"
                },
                {
                    "facetName": "processes",
                    "id": "16909c29-4da3-4bbf-a721-6a2cb721efb7",
                    "creationId": "5e625082-ffc0-43d5-843e-547f64fd447a",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/16909c29-4da3-4bbf-a721-6a2cb721efb7"
                },
                {
                    "facetName": "processes",
                    "id": "218c8a5a-4716-4b9f-a985-44faf3a94ac3",
                    "creationId": "6ba15f74-9fad-4cbd-b51d-eb09255f9125",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/218c8a5a-4716-4b9f-a985-44faf3a94ac3"
                }
            ]
        }
    ]
}
```

### Get a the root path elements of a specific element from the *tree* view of the *processes* facet

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/cd5e6ffa-53fd-4167-97e0-a7f9a974d00a?$resources=rootPath
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "49f82ee7-9fe0-4ab1-86ed-0e6c13091dc7",
            "versionId": "f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5",
            "rootPath": [
                {
                    "facetName": "processes",
                    "id": "d7b81b45-743e-4dd5-9fe4-94293ddde5e7",
                    "versionId": "d8aa3b14-4b9f-41ae-8991-be9fc47dcef0",
                    "type": "mainProcess",
                    "state": "inEffect",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/d8aa3b14-4b9f-41ae-8991-be9fc47dcef0"
                },
                {
                    "facetName": "processes",
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                },
                {
                    "facetName": "processes",
                    "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
                    "creationId": "ab2835f8-da30-4e36-a863-456e1105bb58",
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
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/tree/elements/7c9b6b04-2a73-4557-97b6-d9b1e490bd5a?$resources=stereotype
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "id": "e1cc921b-c8e4-49c9-b9e8-027542eb1716",
            "versionId": "7c9b6b04-2a73-4557-97b6-d9b1e490bd5a",
            "type": "system",
            "state": "released",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
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

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
