---
uid: content
---
# Content

**api-version**: 1.0

Retrieves the content of an element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/content
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
| values | [Element[]](#element) | The list of elements. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the content of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/1a526d30-f0c4-11df-4e21-001c25729284/content
```

#### Reponse (200 OK)
```json
{
    "count": 12,
    "values": [
        {
            "id": "c3f18a4b-7b03-4b53-888d-9961087ac6ba",
            "type": "func",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/c3f18a4b-7b03-4b53-888d-9961087ac6ba/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "6c731872-da73-11de-7d13-0022681385fe",
                        "type": "ruleXor"
                    }
                ]
            }
        },
        {
            "id": "a9e92cb2-c7cc-4b6b-886e-31df931fceb4",
            "type": "func",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/a9e92cb2-c7cc-4b6b-886e-31df931fceb4/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "6c72f169-da73-11de-7d13-0022681385fe",
                        "type": "ruleXor"
                    }
                ]
            }
        },
        {
            "id": "99d51358-39e4-4b66-ab52-dd8066f7a9aa",
            "type": "func",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/99d51358-39e4-4b66-ab52-dd8066f7a9aa/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "d1068af8-21df-4153-9d8d-e8d523ce148b",
                        "type": "func"
                    }
                ]
            }
        },
        {
            "id": "8cf4b9ff-361b-4e03-a6f8-73d2bcc59b8d",
            "type": "func",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/8cf4b9ff-361b-4e03-a6f8-73d2bcc59b8d/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "6c731872-da73-11de-7d13-0022681385fe",
                        "type": "ruleXor"
                    }
                ]
            }
        },
        {
            "id": "4ede9e9b-ae9f-4bf2-a52e-ca2347792f41",
            "type": "evEnd",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/4ede9e9b-ae9f-4bf2-a52e-ca2347792f41/TreeAndDiagram",
            "properties": {
                "predecessors": []
            }
        },
        {
            "id": "6c72f169-da73-11de-7d13-0022681385fe",
            "type": "ruleXor",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/6c72f169-da73-11de-7d13-0022681385fe/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "2221e493-cde2-4c7f-9901-6f55bf736307",
                        "type": "funcCondition"
                    },
                    {
                        "id": "fc816519-f977-4114-bb8a-e924bf78c334",
                        "type": "funcCondition"
                    }
                ]
            }
        },
        {
            "id": "6c731872-da73-11de-7d13-0022681385fe",
            "type": "ruleXor",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/6c731872-da73-11de-7d13-0022681385fe/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "4ede9e9b-ae9f-4bf2-a52e-ca2347792f41",
                        "type": "evEnd"
                    }
                ]
            }
        },
        {
            "id": "2221e493-cde2-4c7f-9901-6f55bf736307",
            "type": "funcCondition",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/2221e493-cde2-4c7f-9901-6f55bf736307/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "99d51358-39e4-4b66-ab52-dd8066f7a9aa",
                        "type": "func"
                    }
                ]
            }
        },
        {
            "id": "fc816519-f977-4114-bb8a-e924bf78c334",
            "type": "funcCondition",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/fc816519-f977-4114-bb8a-e924bf78c334/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "8388a2b7-bf25-4cda-a8ef-50e3779091aa",
                        "type": "func"
                    }
                ]
            }
        },
        {
            "id": "96d62177-da6c-4df3-999c-38e6573b328e",
            "type": "evStart",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/96d62177-da6c-4df3-999c-38e6573b328e/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "a9e92cb2-c7cc-4b6b-886e-31df931fceb4",
                        "type": "func"
                    }
                ]
            }
        },
        {
            "id": "8388a2b7-bf25-4cda-a8ef-50e3779091aa",
            "type": "func",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/8388a2b7-bf25-4cda-a8ef-50e3779091aa/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "c3f18a4b-7b03-4b53-888d-9961087ac6ba",
                        "type": "func"
                    }
                ]
            }
        },
        {
            "id": "d1068af8-21df-4153-9d8d-e8d523ce148b",
            "type": "func",
            "expandUri": "https://demo.symbioworld.com/pz/showcase/_api/data/Processes/d1068af8-21df-4153-9d8d-e8d523ce148b/TreeAndDiagram",
            "properties": {
                "predecessors": [
                    {
                        "id": "8cf4b9ff-361b-4e03-a6f8-73d2bcc59b8d",
                        "type": "func"
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

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
