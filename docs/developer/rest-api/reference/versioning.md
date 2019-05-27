# Versioning

**api-version**: 4.0

Retrieves a version for specific element.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/versions
```

With optional parameters

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/versions?$filter={filter}&$select={select}&$expandRelated={expand}
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

### Get a version for specific element from the *detail* view of the *processes* facet

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/1b154523-68ad-4138-9a24-9076062a51b7/versions
```

#### Response (200 OK)
```json
{
    "count": 3,
    "elements": [
        {
            "facetName": "processes",
            "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
            "versionId": "ed0b7953-ab87-4194-ada6-60e64dc41d74",
            "type": "subProcess",
            "state": "expired",
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
                    "127": "2019-05-22T15:57:46.8643061"
                },
                "createdOn": {
                    "127": "2019-05-22T15:56:50.8268224"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/ed0b7953-ab87-4194-ada6-60e64dc41d74",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/ed0b7953-ab87-4194-ada6-60e64dc41d74"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Sub1",
                    "1033": "Sub1"
                },
                "reasonForRevision": {
                    "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>0.1</p>"
                },
                "relOn": {
                    "127": "2019-05-22T15:57:27.2395307"
                },
                "state1": {
                    "127": "expired"
                },
                "validFrom": {
                    "127": "2019-05-22T00:00:00"
                },
                "validUntil": {
                    "127": "2019-05-22T00:00:00"
                },
                "version": {
                    "127": "1.0"
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
                        "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
                        "versionId": "ed0b7953-ab87-4194-ada6-60e64dc41d74",
                        "type": "subProcess",
                        "state": "expired",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ed0b7953-ab87-4194-ada6-60e64dc41d74"
                    },
                    {
                        "facetName": "processes",
                        "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
                        "versionId": "a309faa0-ac93-4cd2-a4f0-59d7d7988aec",
                        "type": "subProcess",
                        "state": "released",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/a309faa0-ac93-4cd2-a4f0-59d7d7988aec"
                    }
                ]
            }
        },
        {
            "facetName": "processes",
            "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
            "versionId": "a309faa0-ac93-4cd2-a4f0-59d7d7988aec",
            "type": "subProcess",
            "state": "released",
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
                    "127": "2019-05-22T15:57:50.4338785"
                },
                "createdOn": {
                    "127": "2019-05-22T15:57:31.270655"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/a309faa0-ac93-4cd2-a4f0-59d7d7988aec",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/a309faa0-ac93-4cd2-a4f0-59d7d7988aec"
                },
                "isReleased": {
                    "127": true
                },
                "name": {
                    "1031": "Sub1",
                    "1033": "Sub1"
                },
                "reasonForRevision": {
                    "127": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>2.0</p>"
                },
                "relOn": {
                    "127": "2019-05-22T15:57:46.5677734"
                },
                "state1": {
                    "127": "released"
                },
                "validFrom": {
                    "127": "2019-05-22T00:00:00"
                },
                "validUntil": {
                    "127": "9999-12-31T00:00:00"
                },
                "version": {
                    "127": "2.0"
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
                        "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
                        "versionId": "ed0b7953-ab87-4194-ada6-60e64dc41d74",
                        "type": "subProcess",
                        "state": "expired",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ed0b7953-ab87-4194-ada6-60e64dc41d74"
                    },
                    {
                        "facetName": "processes",
                        "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
                        "versionId": "a309faa0-ac93-4cd2-a4f0-59d7d7988aec",
                        "type": "subProcess",
                        "state": "released",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/a309faa0-ac93-4cd2-a4f0-59d7d7988aec"
                    }
                ]
            }
        },
        {
            "facetName": "processes",
            "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
            "versionId": "1b154523-68ad-4138-9a24-9076062a51b7",
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
                    "127": "2019-05-22T15:57:50.9387695"
                },
                "createdOn": {
                    "127": "2019-05-22T15:57:49.8389161"
                },
                "gotoUrl": {
                    "1031": "https://demo.symbioworld.com/pz/showcase/1031/BasePlugin/GoTo/Processes/treeanddiagram/1b154523-68ad-4138-9a24-9076062a51b7",
                    "1033": "https://demo.symbioworld.com/pz/showcase/1033/BasePlugin/GoTo/Processes/treeanddiagram/1b154523-68ad-4138-9a24-9076062a51b7"
                },
                "isReleased": {
                    "127": false
                },
                "name": {
                    "1031": "Sub1",
                    "1033": "Sub1"
                },
                "state1": {
                    "127": "inProcess"
                },
                "validUntil": {
                    "127": "9999-12-31T00:00:00"
                },
                "version": {
                    "127": "2.1"
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
                        "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                        "type": "user",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074"
                    }
                ],
                "releaseHistory": [
                    {
                        "facetName": "processes",
                        "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
                        "versionId": "ed0b7953-ab87-4194-ada6-60e64dc41d74",
                        "type": "subProcess",
                        "state": "expired",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/ed0b7953-ab87-4194-ada6-60e64dc41d74"
                    },
                    {
                        "facetName": "processes",
                        "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
                        "versionId": "a309faa0-ac93-4cd2-a4f0-59d7d7988aec",
                        "type": "subProcess",
                        "state": "released",
                        "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/a309faa0-ac93-4cd2-a4f0-59d7d7988aec"
                    }
                ]
            }
        }
    ]
}
```



### Get a version for specific element from the *detail* view of the *processes* facet and only include the attributes *name* and *author*

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/elements/1b154523-68ad-4138-9a24-9076062a51b7/versions?$select=name,author
```

#### Response (200 OK)
```json
{
    "count": 3,
    "elements": [
        {
            "facetName": "processes",
            "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
            "versionId": "ed0b7953-ab87-4194-ada6-60e64dc41d74",
            "type": "subProcess",
            "state": "expired",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "name": {
                    "1031": "Sub1",
                    "1033": "Sub1"
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
            }
        },
        {
            "facetName": "processes",
            "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
            "versionId": "a309faa0-ac93-4cd2-a4f0-59d7d7988aec",
            "type": "subProcess",
            "state": "released",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "name": {
                    "1031": "Sub1",
                    "1033": "Sub1"
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
            }
        },
        {
            "facetName": "processes",
            "id": "f8013714-185e-459a-86d3-fcf05b7570cd",
            "versionId": "1b154523-68ad-4138-9a24-9076062a51b7",
            "type": "subProcess",
            "state": "inProcess",
            "displayNames": {
            "1031": "Sub Process",
            "1033": "sub process"
            },
            "attributes": {
                "name": {
                    "1031": "Sub1",
                    "1033": "Sub1"
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
