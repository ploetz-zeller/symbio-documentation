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
| values | [ElementCollection](#element) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresulttype) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/release/664fd624-d341-4521-b430-897bb16399f4/transitions/ReleasedToRequestToExpire
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "096724b9-5cab-4ff0-890d-69ea65ac6de7",
            "versionId": "40045b2b-413c-4289-a919-11f89af037fb",
            "type": "subProcess",
            "state": "released",
            "attributes": {
                "authorNote": {
                    "1031": "Ein oder mehrere Autoren wurden gesetzt. Nur Architekten und die angegebenen Autoren dürfen das aktuelle Element bearbeiten.",
                    "1033": "The author was set. Only architects and the defined authors are allowed to edit the current element."
                },
                "changedOn": {
                    "127": "2019-05-22T12:04:14.9195116"
                },
                "createdOn": {
                    "127": "2019-05-22T11:57:32"
                },
                "name": {
                    "1031": "SubProcess",
                    "1033": "SubProcess"
                },
                "reasonForRevision": {
                    "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>need to be released</p>"
                },
                "relOn": {
                    "127": "2019-05-22T12:03:54.8308905"
                },
                "state1": {
                    "127": "released"
                },
                "validFrom": {
                    "127": "2019-05-22T00:00:00"
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
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "changedBy": [
                    {
                        "facetName": "automation",
                        "id": "7a827f97-b970-49fd-97bf-02ecda1b3cfb",
                        "creationId": "7a827f97-b970-49fd-97bf-02ecda1b3cfb",
                        "type": "authToken",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/automation/views/detail/elements/7a827f97-b970-49fd-97bf-02ecda1b3cfb"
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
                "owner": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "qualityManager": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "relBy": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "releaseHistory": [
                    {
                        "facetName": "processes",
                        "id": "096724b9-5cab-4ff0-890d-69ea65ac6de7",
                        "versionId": "40045b2b-413c-4289-a919-11f89af037fb",
                        "type": "subProcess",
                        "state": "released",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/40045b2b-413c-4289-a919-11f89af037fb"
                    }
                ],
                "reviewer": [
                    {
                        "facetName": "users",
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "secondaryAuthors": [
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

!!! info
    After successfully "ReleasedToRequestToExpire" transition for Sub Process, new task will appear in header "My tasks(1)". It will be added new "Approve expiry" action type that must be accepted to complete the transition.



## Definitions

### Element
{!developer/rest-api/reference/models/element.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}