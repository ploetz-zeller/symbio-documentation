# Attributes list

**api-version**: 1.0

Retrieves the list of attributes.

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes
```

With optional parameters

```
GET /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes?$filter={filter}&$select={select}
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
| $select | query | | string | A comma separated list of namesof the attributes/related contexts to include. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [Attribute[]](#attribute) | The list of attributes. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the list of attributes of an element

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/attributes
```

#### Response (200 OK)
```json
{
    "count": 14,
    "values": {
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
    }
}
```

### Get the *name* and *description* attributes of an element

#### Request
```
GET https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/f4f3943d-6b3b-42a9-8a3a-30acf42ce7d5/attributes?$select=name,description
```

#### Response (200 OK)
```json
{
    "count": 2,
    "values": {
        "description": {
            "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>Der Innovations- und Anforderungsprozess gliedert sich in drei Phasen:</p><ul>\n<li>Impulsphase: Beobachtung von Trends, Ideenfindung, Brainstorming von Anforderungen, Kundenanforderungen</li>\n<li>Bewertungsphase: Prüfung auf Tauglichkeit der Idee für das jeweilige Produkt und den Marktanforderungen</li>\n<li>Technologietransfer: Anforderungen in die Release-Planung überführen</li>\n</ul></div>",
            "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>The Innovation and request process is divided into three phases:</p><ul>\n<li>Pulse phase: review of trends, ideas, brainstorming of requirements, customer requirements</li>\n<li>Evaluation phase: testing for suitability of the idea for the product and market requirements</li>\n<li>Technology transfer: transfer requirements in the release planning</li>\n</ul></div>"
        },
        "name": {
            "1031": "Ideen/Innovationen",
            "1033": "Idea/Innovation"
        }
    }
}
```

## Definitions

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
