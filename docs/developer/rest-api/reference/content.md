# Content

**api-version**: 2.0

Retrieves the content of an element.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/content
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
| elements | [ElementCollection](#elementcollection) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the content of an element

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/664fd624-d341-4521-b430-897bb16399f4/content
```

#### Response (200 OK)
```json
{
    "count": 10,
    "elements": [
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "20e54882-843f-466d-901d-1bd97f4faa92"
                        },
                        "facetName": "processes",
                        "id": "c306e185-d594-4d41-94ca-87062a978b26",
                        "creationId": "c306e185-d594-4d41-94ca-87062a978b26",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c306e185-d594-4d41-94ca-87062a978b26"
                    }
                ],
                "shapeId": "f30dfae5-4230-496b-9098-9b6a334fd4ae"
            },
            "facetName": "processes",
            "id": "74c8bc48-0aca-4973-90c0-146c16874475",
            "creationId": "74c8bc48-0aca-4973-90c0-146c16874475",
            "type": "task",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/f30dfae5-4230-496b-9098-9b6a334fd4ae",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/f30dfae5-4230-496b-9098-9b6a334fd4ae"
                },
                "name": {
                    "1031": "Ergebnisse\nkommunizieren",
                    "1033": "Communicare results"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "c35d07bc-8569-4c7d-98e2-0a60e6515f65"
                        },
                        "facetName": "processes",
                        "id": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "creationId": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "type": "ruleAnd",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a64e2b1-7025-4465-8eae-e0b8d3c8eafc"
                    }
                ],
                "shapeId": "87414561-2b72-41c8-8ed7-bb5a34161c64"
            },
            "facetName": "processes",
            "id": "26616754-1dc6-4a72-b701-ce9747102ad6",
            "creationId": "26616754-1dc6-4a72-b701-ce9747102ad6",
            "type": "task",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/87414561-2b72-41c8-8ed7-bb5a34161c64",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/87414561-2b72-41c8-8ed7-bb5a34161c64"
                },
                "name": {
                    "1031": "Kunden-\nanforderungen\nzusammenführen",
                    "1033": "Consolidate customer requirements"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "13957aa4-971c-46c3-bca2-35918fd7f002"
                        },
                        "facetName": "processes",
                        "id": "d7abb4f9-e15d-4d6e-962a-a7b14c8f3746",
                        "creationId": "d7abb4f9-e15d-4d6e-962a-a7b14c8f3746",
                        "type": "evStart",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/d7abb4f9-e15d-4d6e-962a-a7b14c8f3746"
                    }
                ],
                "shapeId": "c35d07bc-8569-4c7d-98e2-0a60e6515f65"
            },
            "facetName": "processes",
            "id": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
            "creationId": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
            "type": "ruleAnd",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/c35d07bc-8569-4c7d-98e2-0a60e6515f65",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/c35d07bc-8569-4c7d-98e2-0a60e6515f65"
                },
                "name": {
                    "1031": "Und",
                    "1033": "And"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "c35d07bc-8569-4c7d-98e2-0a60e6515f65"
                        },
                        "facetName": "processes",
                        "id": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "creationId": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "type": "ruleAnd",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a64e2b1-7025-4465-8eae-e0b8d3c8eafc"
                    }
                ],
                "shapeId": "cfbcc10b-2b20-4766-84fb-d2ac82f4061d"
            },
            "facetName": "processes",
            "id": "84a8eee0-8426-417b-9870-2f7365b3272b",
            "creationId": "84a8eee0-8426-417b-9870-2f7365b3272b",
            "type": "task",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/cfbcc10b-2b20-4766-84fb-d2ac82f4061d",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/cfbcc10b-2b20-4766-84fb-d2ac82f4061d"
                },
                "name": {
                    "1031": "Markt-\nanforderungen\nanalysieren",
                    "1033": "Analyze market requirements"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "943ce351-d828-4287-913f-d9af31618299"
                        },
                        "facetName": "processes",
                        "id": "be1291b0-5883-4b07-be8e-185dc917cd36",
                        "creationId": "be1291b0-5883-4b07-be8e-185dc917cd36",
                        "type": "ruleAnd",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/be1291b0-5883-4b07-be8e-185dc917cd36"
                    }
                ],
                "shapeId": "20e54882-843f-466d-901d-1bd97f4faa92"
            },
            "facetName": "processes",
            "id": "c306e185-d594-4d41-94ca-87062a978b26",
            "creationId": "c306e185-d594-4d41-94ca-87062a978b26",
            "type": "task",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/20e54882-843f-466d-901d-1bd97f4faa92",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/20e54882-843f-466d-901d-1bd97f4faa92"
                },
                "name": {
                    "1031": "Ergebnisse\nzusammenführen",
                    "1033": "Consolidate results"
                }
            },
            "related": {
                "hasInput": [
                    {
                        "facetName": "inputsoutputs",
                        "id": "56088292-6424-45b1-a82f-c8b344b1251a",
                        "versionId": "3f8cd15f-c095-4538-b1c2-518784a02215",
                        "type": "inOut",
                        "state": "inEffect",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/3f8cd15f-c095-4538-b1c2-518784a02215"
                    },
                    {
                        "facetName": "inputsoutputs",
                        "id": "87fa70ad-5d3a-4311-9d6d-3b6494f06b4c",
                        "versionId": "4468c587-6331-4229-be6b-8463372d96ce",
                        "type": "inOut",
                        "state": "inEffect",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/4468c587-6331-4229-be6b-8463372d96ce"
                    }
                ],
                "hasOutput": [
                    {
                        "facetName": "inputsoutputs",
                        "id": "11db4543-6950-4213-9704-08339138015f",
                        "versionId": "12ee8876-31dc-4cde-8dc6-3374eda6cb02",
                        "type": "inOut",
                        "state": "inEffect",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views/detail/elements/12ee8876-31dc-4cde-8dc6-3374eda6cb02"
                    }
                ],
                "systems": [
                    {
                        "facetName": "it",
                        "id": "fa23751e-9ce9-4b34-8125-7cc4f9580867",
                        "versionId": "d5dfae5a-698c-4896-a1d3-8512e2c4e485",
                        "type": "system",
                        "state": "inEffect",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views/detail/elements/d5dfae5a-698c-4896-a1d3-8512e2c4e485",
                        "stereotype": "applicationSystem"
                    }
                ]
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "c35d07bc-8569-4c7d-98e2-0a60e6515f65"
                        },
                        "facetName": "processes",
                        "id": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "creationId": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "type": "ruleAnd",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a64e2b1-7025-4465-8eae-e0b8d3c8eafc"
                    }
                ],
                "shapeId": "b782450a-49a9-460c-b55c-ab35a3b12ca7"
            },
            "facetName": "processes",
            "id": "f45698d5-2dfb-43a7-8a9d-98d1c8a1d829",
            "creationId": "f45698d5-2dfb-43a7-8a9d-98d1c8a1d829",
            "type": "task",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/b782450a-49a9-460c-b55c-ab35a3b12ca7",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/b782450a-49a9-460c-b55c-ab35a3b12ca7"
                },
                "name": {
                    "1031": "Ergebnisse \nInnovations-\nWorkshop\nintegrieren",
                    "1033": "Integrate results of innovation workshop"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "c35d07bc-8569-4c7d-98e2-0a60e6515f65"
                        },
                        "facetName": "processes",
                        "id": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "creationId": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                        "type": "ruleAnd",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a64e2b1-7025-4465-8eae-e0b8d3c8eafc"
                    }
                ],
                "shapeId": "f099f80f-abfa-4b4d-af0c-c31a48a99000"
            },
            "facetName": "processes",
            "id": "e31e33f2-8d0e-4009-862d-3802866ef152",
            "creationId": "e31e33f2-8d0e-4009-862d-3802866ef152",
            "type": "task",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/f099f80f-abfa-4b4d-af0c-c31a48a99000",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/f099f80f-abfa-4b4d-af0c-c31a48a99000"
                },
                "name": {
                    "1031": "Wettbewerb\nanalysieren",
                    "1033": "Analyse competition"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "f30dfae5-4230-496b-9098-9b6a334fd4ae"
                        },
                        "facetName": "processes",
                        "id": "74c8bc48-0aca-4973-90c0-146c16874475",
                        "creationId": "74c8bc48-0aca-4973-90c0-146c16874475",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/74c8bc48-0aca-4973-90c0-146c16874475"
                    }
                ],
                "shapeId": "f93c340a-1d40-49e3-b837-fad884bc93da"
            },
            "facetName": "processes",
            "id": "a21001f1-740b-492a-8aa0-ef9d87098f5e",
            "creationId": "a21001f1-740b-492a-8aa0-ef9d87098f5e",
            "type": "evEnd",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/f93c340a-1d40-49e3-b837-fad884bc93da",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/f93c340a-1d40-49e3-b837-fad884bc93da"
                },
                "name": {
                    "1031": "Ende",
                    "1033": "End"
                }
            }
        },
        {
            "properties": {
                "predecessors": [
                    {
                        "properties": {
                            "shapeId": "87414561-2b72-41c8-8ed7-bb5a34161c64"
                        },
                        "facetName": "processes",
                        "id": "26616754-1dc6-4a72-b701-ce9747102ad6",
                        "creationId": "26616754-1dc6-4a72-b701-ce9747102ad6",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/26616754-1dc6-4a72-b701-ce9747102ad6"
                    },
                    {
                        "properties": {
                            "shapeId": "b782450a-49a9-460c-b55c-ab35a3b12ca7"
                        },
                        "facetName": "processes",
                        "id": "f45698d5-2dfb-43a7-8a9d-98d1c8a1d829",
                        "creationId": "f45698d5-2dfb-43a7-8a9d-98d1c8a1d829",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f45698d5-2dfb-43a7-8a9d-98d1c8a1d829"
                    },
                    {
                        "properties": {
                            "shapeId": "f099f80f-abfa-4b4d-af0c-c31a48a99000"
                        },
                        "facetName": "processes",
                        "id": "e31e33f2-8d0e-4009-862d-3802866ef152",
                        "creationId": "e31e33f2-8d0e-4009-862d-3802866ef152",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/e31e33f2-8d0e-4009-862d-3802866ef152"
                    },
                    {
                        "properties": {
                            "shapeId": "cfbcc10b-2b20-4766-84fb-d2ac82f4061d"
                        },
                        "facetName": "processes",
                        "id": "84a8eee0-8426-417b-9870-2f7365b3272b",
                        "creationId": "84a8eee0-8426-417b-9870-2f7365b3272b",
                        "type": "task",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/84a8eee0-8426-417b-9870-2f7365b3272b"
                    }
                ],
                "shapeId": "943ce351-d828-4287-913f-d9af31618299"
            },
            "facetName": "processes",
            "id": "be1291b0-5883-4b07-be8e-185dc917cd36",
            "creationId": "be1291b0-5883-4b07-be8e-185dc917cd36",
            "type": "ruleAnd",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/943ce351-d828-4287-913f-d9af31618299",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/943ce351-d828-4287-913f-d9af31618299"
                },
                "name": {
                    "1031": "Und",
                    "1033": "And"
                }
            }
        },
        {
            "properties": {
                "predecessors": [],
                "shapeId": "13957aa4-971c-46c3-bca2-35918fd7f002"
            },
            "facetName": "processes",
            "id": "d7abb4f9-e15d-4d6e-962a-a7b14c8f3746",
            "creationId": "d7abb4f9-e15d-4d6e-962a-a7b14c8f3746",
            "type": "evStart",
            "attributes": {
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/13957aa4-971c-46c3-bca2-35918fd7f002",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram//d1c46bcb-2fdd-430b-b155-671d21efbe2a/664fd624-d341-4521-b430-897bb16399f4/13957aa4-971c-46c3-bca2-35918fd7f002"
                },
                "name": {
                    "1031": "Start",
                    "1033": "Start"
                }
            }
        }
    ]
}
```

## Definitions

### Element
{!developer/rest-api/reference/models/element.md!}

### ElementCollection
{!developer/rest-api/reference/models/elementcollection.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
