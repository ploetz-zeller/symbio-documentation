# Change state

**api-version**: 1.0

Change the state of a specific element.

```
POST /{collectionId}/{storageId}/_api/release/{elementId}/transitions/{transitionId}
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/release/{elementId}/transitions/{transitionId}?ignoreWarnings={ignoreWarnings}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| elementId | path | true | string | The ID of the element. |
| transitionId | path | true | string | The ID of the transition. |
| ignoreWarnings | path | true | boolean [true, false] | Ignore validation warnings. |

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

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/release/664fd624-d341-4521-b430-897bb16399f4/transitions/ReleasedToRequestToExpire
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
            "versionId": "664fd624-d341-4521-b430-897bb16399f4",
            "type": "subProcess",
            "state": "requestToExpire",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2018-10-19T14:31:11.1755961"
                },
                "createdOn": {
                    "127": "2015-11-28T17:31:09"
                },
                "name": {
                    "1031": "Produktweiterentwicklung strategisch planen",
                    "1033": "Plan product development strategically"
                },
                "processMaturity": {
                    "127": "implemented"
                },
                "reasonForRevision": {
                    "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>Translation completed for english version</p>"
                },
                "relOn": {
                    "127": "2017-05-19T15:42:06"
                },
                "state1": {
                    "127": "requestToExpire"
                },
                "validFrom": {
                    "127": "2017-05-19T00:00:00"
                },
                "validUntil": {
                    "127": "2018-05-19T00:00:00"
                }
            },
            "related": {
                "author": [
                    {
                        "id": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "creationId": "ab01a052-80f2-4fbf-8e21-698cb7095b34",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/ab01a052-80f2-4fbf-8e21-698cb7095b34"
                    }
                ],
                "changedBy": [
                    {
                        "id": "1cb15b4b-1f26-4d55-afc7-caa215e24c58",
                        "creationId": "1cb15b4b-1f26-4d55-afc7-caa215e24c58",
                        "type": "authToken",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/automation/views/detail/elements/1cb15b4b-1f26-4d55-afc7-caa215e24c58"
                    }
                ],
                "createdBy": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "organisations": [
                    {
                        "id": "8eaf0377-8a36-410f-b77b-e0c1f3a8e88f",
                        "versionId": "2804d525-f6d7-47b2-b76f-dcf27dbac888",
                        "type": "orgUnit",
                        "state": "released",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/organization/views/detail/elements/2804d525-f6d7-47b2-b76f-dcf27dbac888",
                        "stereotype": {
                            "id": "2520e2a7-0acc-491f-9c4a-607c9ff61d47",
                            "creationId": "2520e2a7-0acc-491f-9c4a-607c9ff61d47",
                            "type": "orgUnitType",
                            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/stereotypes/views/detail/elements/2520e2a7-0acc-491f-9c4a-607c9ff61d47"
                        }
                    }
                ],
                "organizationFilters": [
                    {
                        "id": "8eaf0377-8a36-410f-b77b-e0c1f3a8e88f",
                        "versionId": "2804d525-f6d7-47b2-b76f-dcf27dbac888",
                        "type": "orgUnit",
                        "state": "released",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/organization/views/detail/elements/2804d525-f6d7-47b2-b76f-dcf27dbac888",
                        "stereotype": {
                            "id": "2520e2a7-0acc-491f-9c4a-607c9ff61d47",
                            "creationId": "2520e2a7-0acc-491f-9c4a-607c9ff61d47",
                            "type": "orgUnitType",
                            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/stereotypes/views/detail/elements/2520e2a7-0acc-491f-9c4a-607c9ff61d47"
                        }
                    }
                ],
                "owner": [
                    {
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ],
                "qualityManager": [
                    {
                        "id": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "creationId": "45b86897-4509-4db3-953f-bf4998f86f4d",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/45b86897-4509-4db3-953f-bf4998f86f4d"
                    }
                ],
                "relBy": [
                    {
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "releaseHistory": [
                    {
                        "id": "d1c46bcb-2fdd-430b-b155-671d21efbe2a",
                        "versionId": "d68d04d8-8fc7-4ed9-8120-a5b6b2b7d59b",
                        "type": "subProcess",
                        "state": "expired",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/d68d04d8-8fc7-4ed9-8120-a5b6b2b7d59b"
                    }
                ]
            },
            "content": [
                {
                    "id": "26616754-1dc6-4a72-b701-ce9747102ad6",
                    "creationId": "26616754-1dc6-4a72-b701-ce9747102ad6",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/26616754-1dc6-4a72-b701-ce9747102ad6"
                },
                {
                    "id": "a21001f1-740b-492a-8aa0-ef9d87098f5e",
                    "creationId": "a21001f1-740b-492a-8aa0-ef9d87098f5e",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/a21001f1-740b-492a-8aa0-ef9d87098f5e"
                },
                {
                    "id": "be1291b0-5883-4b07-be8e-185dc917cd36",
                    "creationId": "be1291b0-5883-4b07-be8e-185dc917cd36",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/be1291b0-5883-4b07-be8e-185dc917cd36"
                },
                {
                    "id": "e31e33f2-8d0e-4009-862d-3802866ef152",
                    "creationId": "e31e33f2-8d0e-4009-862d-3802866ef152",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/e31e33f2-8d0e-4009-862d-3802866ef152"
                },
                {
                    "id": "c306e185-d594-4d41-94ca-87062a978b26",
                    "creationId": "c306e185-d594-4d41-94ca-87062a978b26",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/c306e185-d594-4d41-94ca-87062a978b26"
                },
                {
                    "id": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                    "creationId": "8a64e2b1-7025-4465-8eae-e0b8d3c8eafc",
                    "type": "ruleAnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/8a64e2b1-7025-4465-8eae-e0b8d3c8eafc"
                },
                {
                    "id": "d7abb4f9-e15d-4d6e-962a-a7b14c8f3746",
                    "creationId": "d7abb4f9-e15d-4d6e-962a-a7b14c8f3746",
                    "type": "evStart",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/d7abb4f9-e15d-4d6e-962a-a7b14c8f3746"
                },
                {
                    "id": "f45698d5-2dfb-43a7-8a9d-98d1c8a1d829",
                    "creationId": "f45698d5-2dfb-43a7-8a9d-98d1c8a1d829",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f45698d5-2dfb-43a7-8a9d-98d1c8a1d829"
                },
                {
                    "id": "84a8eee0-8426-417b-9870-2f7365b3272b",
                    "creationId": "84a8eee0-8426-417b-9870-2f7365b3272b",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/84a8eee0-8426-417b-9870-2f7365b3272b"
                },
                {
                    "id": "74c8bc48-0aca-4973-90c0-146c16874475",
                    "creationId": "74c8bc48-0aca-4973-90c0-146c16874475",
                    "type": "task",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/74c8bc48-0aca-4973-90c0-146c16874475"
                }
            ]
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