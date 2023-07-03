# Related get

**api-version**: 1.0

Retrieves a specific related contexts.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/related/{relatedId}
```

With optional parameters

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/related?$filter={filter}&$expandRelated={expand}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| elementId | path | true | string | The ID of the element. |
| relatedId | path | true | string | The name of the related context. |
| $filter | query | | string | |
| $expandRelated | query | | string | A comma separated list of names of the related contexts to expand. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [ElementCollection](#element) | The list of related elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the *author* related context of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/related/author
```

#### Response (200 OK)
```json
{
    "count": 1,
    "values": {
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
```

### Get and expand the *author* related contexts of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/related/author?$expandRelated=author
```

#### Response (200 OK)
```json
{
    "count": 1,
    "values": {
        "author": [
            {
                "facetName": "users",
                "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "type": "user",
                "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views/detail/elements/a364f30b-a126-4a74-9e1a-1df87f2a6074",
                "related": {
                    "changedBy": [
                        {
                            "facetName": "users",
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user",
                            "attributes": {
                                "changedOn": {
                                    "127": "2019-04-25T14:48:22"
                                },
                                "createdOn": {
                                    "127": "2016-06-13T09:11:49"
                                },
                                "filterInformation": {
                                    "1031": "Keine Filter angewendet",
                                    "1033": "No filter applied"
                                },
                                "firstName": {
                                    "127": "Symbio"
                                },
                                "lastName": {
                                    "127": "Administrator"
                                },
                                "roleAdministrator": {
                                    "127": true
                                },
                                "roleAnalyzer": {
                                    "127": true
                                },
                                "roleApprover": {
                                    "127": true
                                },
                                "roleArchitect": {
                                    "127": true
                                },
                                "roleEditor": {
                                    "127": true
                                },
                                "roleInactive": {
                                    "127": false
                                },
                                "roleViewer": {
                                    "127": true
                                },
                                "userFirstLogin": {
                                    "127": "2018-04-06T12:09:08"
                                },
                                "userLastLogin": {
                                    "127": "2019-04-25T14:48:22"
                                },
                                "userLoginCount": {
                                    "127": 445
                                }
                            }
                        }
                    ],
                    "createdBy": [
                        {
                            "facetName": "users",
                            "id": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "creationId": "a364f30b-a126-4a74-9e1a-1df87f2a6074",
                            "type": "user",
                            "attributes": {
                                "changedOn": {
                                    "127": "2019-04-25T14:48:22"
                                },
                                "createdOn": {
                                    "127": "2016-06-13T09:11:49"
                                },
                                "filterInformation": {
                                    "1031": "Keine Filter angewendet",
                                    "1033": "No filter applied"
                                },
                                "firstName": {
                                    "127": "Symbio"
                                },
                                "lastName": {
                                    "127": "Administrator"
                                },
                                "roleAdministrator": {
                                    "127": true
                                },
                                "roleAnalyzer": {
                                    "127": true
                                },
                                "roleApprover": {
                                    "127": true
                                },
                                "roleArchitect": {
                                    "127": true
                                },
                                "roleEditor": {
                                    "127": true
                                },
                                "roleInactive": {
                                    "127": false
                                },
                                "roleViewer": {
                                    "127": true
                                },
                                "userFirstLogin": {
                                    "127": "2018-04-06T12:09:08"
                                },
                                "userLastLogin": {
                                    "127": "2019-04-25T14:48:22"
                                },
                                "userLoginCount": {
                                    "127": 445
                                }
                            }
                        }
                    ],
                    "hasCulture": [
                        {
                            "facetName": "cultures",
                            "id": "A67E06B1-D942-44E4-B886-CF11931ED8B7",
                            "creationId": "A67E06B1-D942-44E4-B886-CF11931ED8B7",
                            "type": "configCulture",
                            "attributes": {
                                "description": {
                                    "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>Deutsch</p>",
                                    "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>German</p>"
                                },
                                "isAvailableForReporting": {
                                    "127": true
                                },
                                "lcid": {
                                    "127": "1031"
                                },
                                "name": {
                                    "1031": "Deutsch",
                                    "1033": "German"
                                }
                            }
                        }
                    ],
                    "hasSecondaryCultures": [
                        {
                            "facetName": "cultures",
                            "id": "8EB0D08D-B332-4E02-A9F4-12F76AEB696C",
                            "creationId": "8EB0D08D-B332-4E02-A9F4-12F76AEB696C",
                            "type": "configCulture",
                            "attributes": {
                                "cultureIsDefault": {
                                    "127": true
                                },
                                "description": {
                                    "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>Englisch</p>",
                                    "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><p>English</p>"
                                },
                                "isAvailableForReporting": {
                                    "127": true
                                },
                                "lcid": {
                                    "127": "1033"
                                },
                                "name": {
                                    "1031": "Englisch",
                                    "1033": "English"
                                }
                            }
                        }
                    ],
                    "userGroups": [
                        {
                            "facetName": "usergroups",
                            "id": "3cb8366f-3424-4e36-ad6e-03ae72d38191",
                            "creationId": "3cb8366f-3424-4e36-ad6e-03ae72d38191",
                            "type": "userGroup",
                            "attributes": {
                                "id": {
                                    "127": "GrpProjectAccess"
                                },
                                "name": {
                                    "1031": "GrpProjectAccess",
                                    "1033": "GrpProjectAccess"
                                }
                            }
                        },
                        {
                            "facetName": "usergroups",
                            "id": "1fe01960-8f0c-4423-928a-30782efd083d",
                            "creationId": "1fe01960-8f0c-4423-928a-30782efd083d",
                            "type": "userGroup",
                            "attributes": {
                                "id": {
                                    "127": "GrpProjectX1"
                                },
                                "name": {
                                    "1031": "GrpProjectX1",
                                    "1033": "GrpProjectX1"
                                }
                            }
                        },
                        {
                            "facetName": "usergroups",
                            "id": "284E0050-25E8-464D-A321-5DA8234679D1",
                            "creationId": "284E0050-25E8-464D-A321-5DA8234679D1",
                            "type": "userGroup",
                            "attributes": {
                                "id": {
                                    "127": "AdminInfo"
                                },
                                "name": {
                                    "1031": "AdminInfo",
                                    "1033": "AdminInfo"
                                }
                            }
                        },
                        {
                            "facetName": "usergroups",
                            "id": "34b87d93-083a-48d0-8891-920ca6e51a3a",
                            "creationId": "34b87d93-083a-48d0-8891-920ca6e51a3a",
                            "type": "userGroup",
                            "attributes": {
                                "id": {
                                    "127": "GrpProjectX2"
                                },
                                "name": {
                                    "1031": "GrpProjectX2",
                                    "1033": "GrpProjectX2"
                                }
                            }
                        },
                        {
                            "facetName": "usergroups",
                            "id": "3c28b40f-7da8-4b70-8b05-0c3cc274833f",
                            "creationId": "3c28b40f-7da8-4b70-8b05-0c3cc274833f",
                            "type": "userGroup",
                            "attributes": {
                                "id": {
                                    "127": "GrpManaging"
                                },
                                "name": {
                                    "1031": "GrpManaging",
                                    "1033": "GrpManaging"
                                }
                            }
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

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
