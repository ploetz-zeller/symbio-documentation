# Create version

**api-version**: 4.0

Create a new version of a specific element.

```
POST /{collectionId}/{storageId}/_api/release/{elementId}/createversion
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| elementId | path | true | string | The ID of the element. |

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

## Examples

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/release/40045b2b-413c-4289-a919-11f89af037fb/createversion
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "096724b9-5cab-4ff0-890d-69ea65ac6de7",
            "versionId": "d6411daa-f3f7-41c7-8ae0-db088bc0095c",
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
                    "127": "2019-05-22T12:15:07.8482494"
                },
                "createdOn": {
                    "127": "2019-05-22T12:15:07.1429324"
                },
                "name": {
                    "1031": "SubProcess",
                    "1033": "SubProcess"
                },
                "state1": {
                    "127": "inProcess"
                },
                "validUntil": {
                    "127": "9999-12-31T00:00:00"
                }
            },
            "related": {
                "author": [
                    {
                        "facetName": "automation",
                        "id": "7a827f97-b970-49fd-97bf-02ecda1b3cfb",
                        "creationId": "7a827f97-b970-49fd-97bf-02ecda1b3cfb",
                        "type": "authToken",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/automation/views/detail/elements/7a827f97-b970-49fd-97bf-02ecda1b3cfb"
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
                        "facetName": "automation",
                        "id": "7a827f97-b970-49fd-97bf-02ecda1b3cfb",
                        "creationId": "7a827f97-b970-49fd-97bf-02ecda1b3cfb",
                        "type": "authToken",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/automation/views/detail/elements/7a827f97-b970-49fd-97bf-02ecda1b3cfb"
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

## Definitions

### Element
{!developer/rest-api/reference/models/element.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
