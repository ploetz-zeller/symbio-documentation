# Elements update

**api-version**: 4.0

Update existing element

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |

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

### Update existing element in the *detail* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements
```

```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "a98a9d95-77d1-4d5d-9178-cf03f617c8df",
            "versionId": "7a8660bc-3935-44dd-9c3c-98fbd7ca8425",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "changedOn": {
                    "127": "2019-05-22T11:12:36"
                },
                "createdOn": {
                    "127": "2019-05-22T10:08:29"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/7a8660bc-3935-44dd-9c3c-98fbd7ca8425",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/7a8660bc-3935-44dd-9c3c-98fbd7ca8425"
                },
                "isReleased": {
                    "127": false
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
                },
                "version": {
                    "127": "0.1"
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
                "owner": [
                    {
                        "facetName": "users",
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            },
            "content": [
                {
                    "facetName": "processes",
                    "id": "9807501f-e1da-41cf-9c31-91e4fa38be43",
                    "creationId": "9807501f-e1da-41cf-9c31-91e4fa38be43",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9807501f-e1da-41cf-9c31-91e4fa38be43"
                },
                {
                    "facetName": "processes",
                    "id": "365732dc-12a9-4405-b461-5472b088c0b6",
                    "creationId": "365732dc-12a9-4405-b461-5472b088c0b6",
                    "type": "evStart",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/365732dc-12a9-4405-b461-5472b088c0b6"
                },
                {
                    "facetName": "processes",
                    "id": "499eda4c-5b1a-4305-a229-abd81ac90cdd",
                    "creationId": "499eda4c-5b1a-4305-a229-abd81ac90cdd",
                    "type": "processInterfacePlaceholder",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/499eda4c-5b1a-4305-a229-abd81ac90cdd"
                },
                {
                    "facetName": "processes",
                    "id": "1a4dad34-eecd-4ebb-a7e4-25a21a5efa3c",
                    "versionId": "fb92ff40-a84b-4879-bce0-0aa24982f23e",
                    "type": "subProcess",
                    "state": "inProcess",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/fb92ff40-a84b-4879-bce0-0aa24982f23e"
                },
                {
                    "facetName": "processes",
                    "id": "9945eda5-abbc-4e40-8b44-d29f37d7146a",
                    "creationId": "9945eda5-abbc-4e40-8b44-d29f37d7146a",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9945eda5-abbc-4e40-8b44-d29f37d7146a"
                }
            ]
        }
    ]
}
```

#### Response (200 OK)
```json
{
    "count": 1,
    "elements": [
        {
            "facetName": "processes",
            "id": "a98a9d95-77d1-4d5d-9178-cf03f617c8df",
            "versionId": "7a8660bc-3935-44dd-9c3c-98fbd7ca8425",
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
                    "127": "2019-05-22T15:08:50.1189714"
                },
                "createdOn": {
                    "127": "2019-05-22T10:08:29"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/7a8660bc-3935-44dd-9c3c-98fbd7ca8425",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/7a8660bc-3935-44dd-9c3c-98fbd7ca8425"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "SubProcess",
                    "1033": "SubProcess"
                },
                "reasonForRevision": {
                    "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>some</p>"
                },
                "state1": {
                    "127": "inProcess"
                },
                "validFrom": {
                    "127": "2019-05-22T00:00:00"
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
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "changedBy": [
                    {
                        "facetName": "automation",
                        "id": "65bc9c65-da32-4d81-ba9f-898a9e09dd91",
                        "creationId": "65bc9c65-da32-4d81-ba9f-898a9e09dd91",
                        "type": "authToken",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/automation/views/detail/elements/65bc9c65-da32-4d81-ba9f-898a9e09dd91"
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
                        "id": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "creationId": "0630c057-6ba7-47fd-a72f-c9bb80bf18b1",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/0630c057-6ba7-47fd-a72f-c9bb80bf18b1"
                    }
                ]
            },
            "content": [
                {
                    "facetName": "processes",
                    "id": "1a4dad34-eecd-4ebb-a7e4-25a21a5efa3c",
                    "versionId": "fb92ff40-a84b-4879-bce0-0aa24982f23e",
                    "type": "subProcess",
                    "state": "inProcess",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/fb92ff40-a84b-4879-bce0-0aa24982f23e"
                },
                {
                    "facetName": "processes",
                    "id": "365732dc-12a9-4405-b461-5472b088c0b6",
                    "creationId": "365732dc-12a9-4405-b461-5472b088c0b6",
                    "type": "evStart",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/365732dc-12a9-4405-b461-5472b088c0b6"
                },
                {
                    "facetName": "processes",
                    "id": "9807501f-e1da-41cf-9c31-91e4fa38be43",
                    "creationId": "9807501f-e1da-41cf-9c31-91e4fa38be43",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9807501f-e1da-41cf-9c31-91e4fa38be43"
                },
                {
                    "facetName": "processes",
                    "id": "499eda4c-5b1a-4305-a229-abd81ac90cdd",
                    "creationId": "499eda4c-5b1a-4305-a229-abd81ac90cdd",
                    "type": "processInterfacePlaceholder",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/499eda4c-5b1a-4305-a229-abd81ac90cdd"
                },
                {
                    "facetName": "processes",
                    "id": "9945eda5-abbc-4e40-8b44-d29f37d7146a",
                    "creationId": "9945eda5-abbc-4e40-8b44-d29f37d7146a",
                    "type": "evEnd",
                    "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/9945eda5-abbc-4e40-8b44-d29f37d7146a"
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
