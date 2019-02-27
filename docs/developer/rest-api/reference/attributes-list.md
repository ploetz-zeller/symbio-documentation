---
uid: attributeslist
---
# Attributes

**api-version**: 1.0

Retrieves the list of attributes.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes
```

With optional parameters

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/attributes?$filter={filter}&$select={select}
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
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the list of attributes of an element

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/attributes
```

#### Reponse (200 OK)
```json
{
    "count": 12,
    "values": {
        "changedOn": {
            "127": "2018-03-07T10:15:40"
        },
        "createdOn": {
            "127": "2007-12-03T00:00:00"
        },
        "description": {
            "1031": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>Der Innovations- und Anforderungsprozess gliedert sich in drei Phasen:</p><ul>\n<li>Impulsphase: Beobachtung von Trends, Ideenfindung, Brainstorming von Anforderungen, Kundenanforderungen</li>\n<li>Bewertungsphase: Prüfung auf Tauglichkeit der Idee für das jeweilige Produkt und den Marktanforderungen</li>\n<li>Technologietransfer: Anforderungen in die Release-Planung überführen</li>\n</ul></div>",
            "1033": "<?xml version=\"1.0\" encoding=\"utf-8\"?><div><p>The Innovation and request process is divided into three phases:</p><ul>\n<li>Pulse phase: review of trends, ideas, brainstorming of requirements, customer requirements</li>\n<li>Evaluation phase: testing for suitability of the idea for the product and market requirements</li>\n<li>Technology transfer: transfer requirements in the release planning</li>\n</ul></div>"
        },
        "name": {
            "1031": "Ideen/Innovationen",
            "1033": "Idea/Innovation"
        },
        "processMaturity": {
            "127": "processIsLived"
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
        "validFrom": {
            "127": "2015-12-01T18:39:48"
        },
        "validFromUntilPastMessage": {
            "1031": "The date \"01.12.2015\" for \"Gültigkeitsstart\" is in the past.\r\nThe date \"31.03.2016\" for \"Gültigkeitsende\" is in the past.\r\n",
            "1033": "The date \"12/1/2015\" for \"Start of Validity\" is in the past.\r\nThe date \"3/31/2016\" for \"End of Validity\" is in the past.\r\n"
        },
        "validUntil": {
            "127": "2016-03-31T00:00:00"
        },
        "workshopImages": {
            "127": [
                {
                    "address": "18077efd-e887-4b26-841d-f2374d8da7c1",
                    "fullAddress": "https://demo.symbioworld.com/pz/showcase/Master/editor/1033/BasePlugin/File/GetFile/18077efd-e887-4b26-841d-f2374d8da7c1.Storage.html",
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
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/attributes?$select=name,description
```

#### Reponse (200 OK)
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

### Element
[!include[](models\element.md)]

### OperationResultType 
[!include[](models\operationresulttype.md)]

### Error
[!include[](models\error.md)]
