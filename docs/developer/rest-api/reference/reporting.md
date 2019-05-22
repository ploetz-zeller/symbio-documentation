# Reporting

**api-version**: 1.0

Get the reporting for whole facet

```
GET  /{collectionId}/{storageId}/_api/rest/facets/{facetId}/reporting
```

Get the reporting for specific element

```
GET  /{collectionId}/{storageId}/_api/rest/facets/{facetId}/reporting/{elementId}
```

## Parameters

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
| $resources | query | | string ["attributes", "related", "children", "content", "rootPath"] | The resources to include. If not specified all resources will be included. |
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

### Get the report of whole facet

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/reporting
```

#### Response (200 OK)
```json
{
    "count": 2,
    "values": [
        {
            "facetName": "processes",
            "id": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "creationId": "ab2835f8-da30-4e36-a863-456e1105bb58",
            "type": "processHouse",
            "attributes": {
                "changedOn": {
                    "127": "2018-10-30T04:09:21"
                },
                "createdOn": {
                    "127": "2016-03-23T13:10:04"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/ab2835f8-da30-4e36-a863-456e1105bb58",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/ab2835f8-da30-4e36-a863-456e1105bb58"
                },
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
                    "attributes": {
                        "changedOn": {
                            "127": "2018-10-07T14:24:19"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                        },
                        "name": {
                            "1031": "Managementprozesse",
                            "1033": "Management Processes"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-11-05T10:03:59"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                        },
                        "name": {
                            "1031": "Kernprozesse",
                            "1033": "Core Processes"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-10-30T04:08:17"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                        },
                        "name": {
                            "1031": "Unterstützungsprozesse",
                            "1033": "Support Processes"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-10-08T15:20:23"
                        },
                        "createdOn": {
                            "127": "2018-10-08T15:18:50"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/5cb80f0d-d94f-4d05-8a64-1d98345d481c"
                        },
                        "name": {
                            "1031": "E2E Scenarios",
                            "1033": "E2E Scenarios"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                }
            ],
            "content": [
                {
                    "facetName": "processes",
                    "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-10-07T14:24:19"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
                        },
                        "name": {
                            "1031": "Managementprozesse",
                            "1033": "Management Processes"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-11-05T10:03:59"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/24c2a5a1-cdb5-40e7-bb59-4e3d9b1a7ee2"
                        },
                        "name": {
                            "1031": "Kernprozesse",
                            "1033": "Core Processes"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-10-30T04:08:17"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/6823ca8f-1a8b-43e8-ae8c-8b2ef3bd0deb"
                        },
                        "name": {
                            "1031": "Unterstützungsprozesse",
                            "1033": "Support Processes"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                    "type": "subCategory",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-10-08T15:20:23"
                        },
                        "createdOn": {
                            "127": "2018-10-08T15:18:50"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/5cb80f0d-d94f-4d05-8a64-1d98345d481c",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/5cb80f0d-d94f-4d05-8a64-1d98345d481c"
                        },
                        "name": {
                            "1031": "E2E Scenarios",
                            "1033": "E2E Scenarios"
                        },
                        "state1": {
                            "127": "show"
                        }
                    }
                }
            ]
        },
        {
            "facetName": "processes",
            "id": "883669b6-83af-4ce9-b532-b0ba929bef71",
            "type": "view",
            "attributes": {
                "changedOn": {
                    "127": "2019-02-26T15:56:52"
                },
                "createdOn": {
                    "127": "2016-03-23T13:10:04"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/883669b6-83af-4ce9-b532-b0ba929bef71",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/883669b6-83af-4ce9-b532-b0ba929bef71"
                },
                "name": {
                    "1031": "View",
                    "1033": "View"
                },
                "state1": {
                    "127": "show"
                },
                "validUntil": {
                    "127": "9999-12-31T00:00:00"
                }
            },
            "related": {
                "author": [
                    {
                        "facetName": "users",
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "facetName": "users",
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "qualityManager": [
                    {
                        "facetName": "users",
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ]
            },
            "children": [
                {
                    "facetName": "processes",
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2017-03-18T17:06:39"
                        },
                        "createdOn": {
                            "127": "2015-11-27T19:46:39"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/c6e90187-b9f6-4787-9932-abfea54f5463",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/c6e90187-b9f6-4787-9932-abfea54f5463"
                        },
                        "name": {
                            "1031": "Supply Chain Overview",
                            "1033": "GeoMap"
                        },
                        "purp": {
                            "1031": "Zeigt übersichtlich auf welche Logistik-Ströme zwischen den Verschiedenen Standort koordiniert werden müssen."
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validFrom": {
                            "127": "2015-11-02T00:00:00"
                        },
                        "validUntil": {
                            "127": "2017-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                                "creationId": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/30fe276f-5312-45e2-ac9d-937437dcbc28"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    }
                },
                {
                    "facetName": "processes",
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2016-10-21T13:40:52"
                        },
                        "createdOn": {
                            "127": "2015-11-27T19:47:03"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                        },
                        "name": {
                            "1031": "ISO 9001:2015",
                            "1033": "ISO 9001"
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validFrom": {
                            "127": "2015-05-04T00:00:00"
                        },
                        "validUntil": {
                            "127": "2018-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    }
                },
                {
                    "facetName": "processes",
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2016-10-21T13:40:53"
                        },
                        "createdOn": {
                            "127": "2015-11-27T19:46:49"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/8db17967-8d30-4b75-9eab-434e85bd7df3",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/8db17967-8d30-4b75-9eab-434e85bd7df3"
                        },
                        "name": {
                            "1031": "SCOR",
                            "1033": "SCOR"
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validFrom": {
                            "127": "2015-11-02T00:00:00"
                        },
                        "validUntil": {
                            "127": "2015-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    }
                },
                {
                    "facetName": "processes",
                    "id": "77181a8e-b6fd-4176-929a-8cafded96cbb",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2019-02-26T15:57:00"
                        },
                        "createdOn": {
                            "127": "2019-02-26T14:17:32"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/77181a8e-b6fd-4176-929a-8cafded96cbb",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/77181a8e-b6fd-4176-929a-8cafded96cbb"
                        },
                        "name": {
                            "1031": "Symbio permissions",
                            "1033": "Symbio permissions"
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validUntil": {
                            "127": "9999-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                                "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                            }
                        ]
                    }
                }
            ],
            "content": [
                {
                    "facetName": "processes",
                    "id": "c6e90187-b9f6-4787-9932-abfea54f5463",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2017-03-18T17:06:39"
                        },
                        "createdOn": {
                            "127": "2015-11-27T19:46:39"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/c6e90187-b9f6-4787-9932-abfea54f5463",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/c6e90187-b9f6-4787-9932-abfea54f5463"
                        },
                        "name": {
                            "1031": "Supply Chain Overview",
                            "1033": "GeoMap"
                        },
                        "purp": {
                            "1031": "Zeigt übersichtlich auf welche Logistik-Ströme zwischen den Verschiedenen Standort koordiniert werden müssen."
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validFrom": {
                            "127": "2015-11-02T00:00:00"
                        },
                        "validUntil": {
                            "127": "2017-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                                "creationId": "30fe276f-5312-45e2-ac9d-937437dcbc28",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/30fe276f-5312-45e2-ac9d-937437dcbc28"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    }
                },
                {
                    "facetName": "processes",
                    "id": "0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2016-10-21T13:40:52"
                        },
                        "createdOn": {
                            "127": "2015-11-27T19:47:03"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/0bcbcd60-1d5b-4c95-a9ef-6e784df55dad"
                        },
                        "name": {
                            "1031": "ISO 9001:2015",
                            "1033": "ISO 9001"
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validFrom": {
                            "127": "2015-05-04T00:00:00"
                        },
                        "validUntil": {
                            "127": "2018-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    }
                },
                {
                    "facetName": "processes",
                    "id": "8db17967-8d30-4b75-9eab-434e85bd7df3",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2016-10-21T13:40:53"
                        },
                        "createdOn": {
                            "127": "2015-11-27T19:46:49"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/8db17967-8d30-4b75-9eab-434e85bd7df3",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/8db17967-8d30-4b75-9eab-434e85bd7df3"
                        },
                        "name": {
                            "1031": "SCOR",
                            "1033": "SCOR"
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validFrom": {
                            "127": "2015-11-02T00:00:00"
                        },
                        "validUntil": {
                            "127": "2015-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    }
                },
                {
                    "facetName": "processes",
                    "id": "77181a8e-b6fd-4176-929a-8cafded96cbb",
                    "type": "view",
                    "attributes": {
                        "changedOn": {
                            "127": "2019-02-26T15:57:00"
                        },
                        "createdOn": {
                            "127": "2019-02-26T14:17:32"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/77181a8e-b6fd-4176-929a-8cafded96cbb",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/77181a8e-b6fd-4176-929a-8cafded96cbb"
                        },
                        "name": {
                            "1031": "Symbio permissions",
                            "1033": "Symbio permissions"
                        },
                        "state1": {
                            "127": "show"
                        },
                        "validUntil": {
                            "127": "9999-12-31T00:00:00"
                        }
                    },
                    "related": {
                        "author": [
                            {
                                "facetName": "users",
                                "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                                "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                            }
                        ]
                    }
                }
            ]
        }
    ]
}
```

### Get the report for specific element

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/reporting/6a50a65b-ba4f-4691-a6c5-e912e6d4063b
```

#### Response (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "facetName": "processes",
            "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
            "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
            "type": "subProcess",
            "state": "inEffect",
            "attributes": {
                "changedOn": {
                    "127": "2018-04-07T12:58:07"
                },
                "createdOn": {
                    "127": "2015-11-28T18:19:59"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                },
                "isLastInProcessOrReleased": {
                    "127": true
                },
                "isReleased": {
                    "127": true
                },
                "isReleasedOrLastInProcess": {
                    "127": true
                },
                "majorVersion": {
                    "127": 1
                },
                "minorVersion": {
                    "127": 0
                },
                "name": {
                    "1031": "Release Planung managen",
                    "1033": "Manage Release Planning"
                },
                "reasonForRevision": {
                    "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>Initiale Prozesserstellung<br /></p>"
                },
                "relOn": {
                    "127": "2018-04-07T12:58:07"
                },
                "state1": {
                    "127": "inEffect"
                },
                "validFrom": {
                    "127": "2018-04-06T00:00:00"
                },
                "validUntil": {
                    "127": "2019-04-06T00:00:00"
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
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "owner": [
                    {
                        "facetName": "users",
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "qualityManager": [
                    {
                        "facetName": "users",
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ]
            },
            "content": [
                {
                    "facetName": "processes",
                    "id": "9a04f3c3-d9f5-4968-9e8f-feb3ed6af7c5",
                    "creationId": "9a04f3c3-d9f5-4968-9e8f-feb3ed6af7c5",
                    "type": "evEnd",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-04-07T12:56:44"
                        },
                        "createdOn": {
                            "127": "2018-04-07T12:56:44"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/b7a5d8ca-fc9d-4530-808c-bb8af5d97733",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/b7a5d8ca-fc9d-4530-808c-bb8af5d97733"
                        },
                        "name": {
                            "1031": "Ende",
                            "1033": "End"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "56b59c80-38dc-4fda-81a4-560cd0db1fe1",
                    "creationId": "56b59c80-38dc-4fda-81a4-560cd0db1fe1",
                    "type": "evStart",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-04-07T12:56:17"
                        },
                        "createdOn": {
                            "127": "2018-04-07T12:56:17"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/4a9eecc5-a2d3-418e-9fae-5dfcc5b8e451",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/4a9eecc5-a2d3-418e-9fae-5dfcc5b8e451"
                        },
                        "name": {
                            "1031": "Start",
                            "1033": "Start"
                        }
                    }
                },
                {
                    "facetName": "processes",
                    "id": "c9f3c367-4e9d-4eeb-90dd-ee569acebcaa",
                    "creationId": "c9f3c367-4e9d-4eeb-90dd-ee569acebcaa",
                    "type": "task",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-04-07T12:56:40"
                        },
                        "createdOn": {
                            "127": "2018-04-07T12:56:20"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/8fb4b72c-3916-4494-be23-87acd153d83c",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/8fb4b72c-3916-4494-be23-87acd153d83c"
                        },
                        "name": {
                            "1031": "Release Planung managen",
                            "1033": "Task"
                        },
                        "validUntil": {
                            "127": "2019-04-07T00:00:00"
                        }
                    }
                }
            ],
            "versions": [
                {
                    "facetName": "processes",
                    "id": "ad112439-f0ef-483a-bab2-4d2a4bb17d00",
                    "versionId": "6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                    "type": "subProcess",
                    "state": "inEffect",
                    "attributes": {
                        "changedOn": {
                            "127": "2018-04-07T12:58:07"
                        },
                        "createdOn": {
                            "127": "2015-11-28T18:19:59"
                        },
                        "gotoUrl": {
                            "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/6a50a65b-ba4f-4691-a6c5-e912e6d4063b",
                            "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/6a50a65b-ba4f-4691-a6c5-e912e6d4063b"
                        },
                        "isLastInProcessOrReleased": {
                            "127": true
                        },
                        "isReleased": {
                            "127": true
                        },
                        "isReleasedOrLastInProcess": {
                            "127": true
                        },
                        "majorVersion": {
                            "127": 1
                        },
                        "minorVersion": {
                            "127": 0
                        },
                        "name": {
                            "1031": "Release Planung managen",
                            "1033": "Manage Release Planning"
                        },
                        "reasonForRevision": {
                            "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>Initiale Prozesserstellung<br /></p>"
                        },
                        "relOn": {
                            "127": "2018-04-07T12:58:07"
                        },
                        "state1": {
                            "127": "inEffect"
                        },
                        "validFrom": {
                            "127": "2018-04-06T00:00:00"
                        },
                        "validUntil": {
                            "127": "2019-04-06T00:00:00"
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
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                            }
                        ],
                        "owner": [
                            {
                                "facetName": "users",
                                "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                            }
                        ],
                        "qualityManager": [
                            {
                                "facetName": "users",
                                "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                                "type": "user",
                                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/reporting/45b86897-4509-4db3-953f-bf4998f86f4d"
                            }
                        ]
                    },
                    "content": [
                        {
                            "facetName": "processes",
                            "id": "9a04f3c3-d9f5-4968-9e8f-feb3ed6af7c5",
                            "creationId": "9a04f3c3-d9f5-4968-9e8f-feb3ed6af7c5",
                            "type": "evEnd",
                            "attributes": {
                                "changedOn": {
                                    "127": "2018-04-07T12:56:44"
                                },
                                "createdOn": {
                                    "127": "2018-04-07T12:56:44"
                                },
                                "gotoUrl": {
                                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/b7a5d8ca-fc9d-4530-808c-bb8af5d97733",
                                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/b7a5d8ca-fc9d-4530-808c-bb8af5d97733"
                                },
                                "name": {
                                    "1031": "Ende",
                                    "1033": "End"
                                }
                            }
                        },
                        {
                            "facetName": "processes",
                            "id": "56b59c80-38dc-4fda-81a4-560cd0db1fe1",
                            "creationId": "56b59c80-38dc-4fda-81a4-560cd0db1fe1",
                            "type": "evStart",
                            "attributes": {
                                "changedOn": {
                                    "127": "2018-04-07T12:56:17"
                                },
                                "createdOn": {
                                    "127": "2018-04-07T12:56:17"
                                },
                                "gotoUrl": {
                                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/4a9eecc5-a2d3-418e-9fae-5dfcc5b8e451",
                                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/4a9eecc5-a2d3-418e-9fae-5dfcc5b8e451"
                                },
                                "name": {
                                    "1031": "Start",
                                    "1033": "Start"
                                }
                            }
                        },
                        {
                            "facetName": "processes",
                            "id": "c9f3c367-4e9d-4eeb-90dd-ee569acebcaa",
                            "creationId": "c9f3c367-4e9d-4eeb-90dd-ee569acebcaa",
                            "type": "task",
                            "attributes": {
                                "changedOn": {
                                    "127": "2018-04-07T12:56:40"
                                },
                                "createdOn": {
                                    "127": "2018-04-07T12:56:20"
                                },
                                "gotoUrl": {
                                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/8fb4b72c-3916-4494-be23-87acd153d83c",
                                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//ad112439-f0ef-483a-bab2-4d2a4bb17d00/6a50a65b-ba4f-4691-a6c5-e912e6d4063b/8fb4b72c-3916-4494-be23-87acd153d83c"
                                },
                                "name": {
                                    "1031": "Release Planung managen",
                                    "1033": "Task"
                                },
                                "validUntil": {
                                    "127": "2019-04-07T00:00:00"
                                }
                            }
                        }
                    ]
                }
            ]
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
