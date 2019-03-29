# Configuration

**api-version**: 1.0

Retrieves the configuration of possible elements in a view.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/config
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
| count | integer | The number of returned types. |
| values | [Type[]](#type) | The list of types. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the configuration of the process list

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/list/config
```

#### Reponse (200 OK)
```json
{
    "count": 11,
    "values": [
        {
            "key": "processHouse",
            "displayNames": {
                "1031": "Prozesshaus",
                "1033": "Process House"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": []
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "subCategory",
            "displayNames": {
                "1031": "Kategorie",
                "1033": "Category"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "show",
                                "displayNames": {
                                    "1031": "Anzeigen",
                                    "1033": "Show"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "mainProcess",
            "displayNames": {
                "1031": "Main Process",
                "1033": "Main Process"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "midProcess",
            "displayNames": {
                "1031": "Mid Process",
                "1033": "Mid Process"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": []
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "subProcess",
            "displayNames": {
                "1031": "Sub Process",
                "1033": "Sub Process"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "inReview",
                                "displayNames": {
                                    "1031": "In Review",
                                    "1033": "In review"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForQa",
                                "displayNames": {
                                    "1031": "Fertig für QA",
                                    "1033": "Ready for QA"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForRelease",
                                "displayNames": {
                                    "1031": "Fertig zur Freigabe",
                                    "1033": "Ready for release"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requestToExpire",
                                "displayNames": {
                                    "1031": "Antrag auf abgelaufen",
                                    "1033": "Request to expire"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "scenario",
            "displayNames": {
                "1031": "Szenario",
                "1033": "Scenario"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "inReview",
                                "displayNames": {
                                    "1031": "In Review",
                                    "1033": "In review"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForQa",
                                "displayNames": {
                                    "1031": "Fertig für QA",
                                    "1033": "Ready for QA"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForRelease",
                                "displayNames": {
                                    "1031": "Fertig zur Freigabe",
                                    "1033": "Ready for release"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requestToExpire",
                                "displayNames": {
                                    "1031": "Antrag auf abgelaufen",
                                    "1033": "Request to expire"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "view",
            "displayNames": {
                "1031": "View",
                "1033": "View"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "show",
                                "displayNames": {
                                    "1031": "Anzeigen",
                                    "1033": "Show"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "createVariantSetting",
            "displayNames": {
                "1031": "ElementType.CreateVariantSetting",
                "1033": "ElementType.CreateVariantSetting"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "inReview",
                                "displayNames": {
                                    "1031": "In Review",
                                    "1033": "In review"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForQa",
                                "displayNames": {
                                    "1031": "Fertig für QA",
                                    "1033": "Ready for QA"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForRelease",
                                "displayNames": {
                                    "1031": "Fertig zur Freigabe",
                                    "1033": "Ready for release"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requestToExpire",
                                "displayNames": {
                                    "1031": "Antrag auf abgelaufen",
                                    "1033": "Request to expire"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "show",
                                "displayNames": {
                                    "1031": "Anzeigen",
                                    "1033": "Show"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "new",
                                "displayNames": {
                                    "1031": "Neu",
                                    "1033": "New"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "disconnected",
                                "displayNames": {
                                    "1031": "Nicht verbunden",
                                    "1033": "Disconnected"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requesting",
                                "displayNames": {
                                    "1031": "Verbindung anfragen",
                                    "1033": "Request connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requested",
                                "displayNames": {
                                    "1031": "Verbindung angefragt",
                                    "1033": "Connection requested"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "accepted",
                                "displayNames": {
                                    "1031": "Verbindung akzeptieren",
                                    "1033": "Accept connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "declined",
                                "displayNames": {
                                    "1031": "Verbindung ablehnen",
                                    "1033": "Decline connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "established",
                                "displayNames": {
                                    "1031": "Verbunden",
                                    "1033": "Established"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "localizeElement",
            "displayNames": {
                "1031": "ElementType.LocalizeElement",
                "1033": "ElementType.LocalizeElement"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "inReview",
                                "displayNames": {
                                    "1031": "In Review",
                                    "1033": "In review"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForQa",
                                "displayNames": {
                                    "1031": "Fertig für QA",
                                    "1033": "Ready for QA"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForRelease",
                                "displayNames": {
                                    "1031": "Fertig zur Freigabe",
                                    "1033": "Ready for release"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requestToExpire",
                                "displayNames": {
                                    "1031": "Antrag auf abgelaufen",
                                    "1033": "Request to expire"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "show",
                                "displayNames": {
                                    "1031": "Anzeigen",
                                    "1033": "Show"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "new",
                                "displayNames": {
                                    "1031": "Neu",
                                    "1033": "New"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "disconnected",
                                "displayNames": {
                                    "1031": "Nicht verbunden",
                                    "1033": "Disconnected"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requesting",
                                "displayNames": {
                                    "1031": "Verbindung anfragen",
                                    "1033": "Request connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requested",
                                "displayNames": {
                                    "1031": "Verbindung angefragt",
                                    "1033": "Connection requested"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "accepted",
                                "displayNames": {
                                    "1031": "Verbindung akzeptieren",
                                    "1033": "Accept connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "declined",
                                "displayNames": {
                                    "1031": "Verbindung ablehnen",
                                    "1033": "Decline connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "established",
                                "displayNames": {
                                    "1031": "Verbunden",
                                    "1033": "Established"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "localizeFlow",
            "displayNames": {
                "1031": "ElementType.LocalizeFlow",
                "1033": "ElementType.LocalizeFlow"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "inReview",
                                "displayNames": {
                                    "1031": "In Review",
                                    "1033": "In review"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForQa",
                                "displayNames": {
                                    "1031": "Fertig für QA",
                                    "1033": "Ready for QA"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForRelease",
                                "displayNames": {
                                    "1031": "Fertig zur Freigabe",
                                    "1033": "Ready for release"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requestToExpire",
                                "displayNames": {
                                    "1031": "Antrag auf abgelaufen",
                                    "1033": "Request to expire"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "show",
                                "displayNames": {
                                    "1031": "Anzeigen",
                                    "1033": "Show"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "new",
                                "displayNames": {
                                    "1031": "Neu",
                                    "1033": "New"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "disconnected",
                                "displayNames": {
                                    "1031": "Nicht verbunden",
                                    "1033": "Disconnected"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requesting",
                                "displayNames": {
                                    "1031": "Verbindung anfragen",
                                    "1033": "Request connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requested",
                                "displayNames": {
                                    "1031": "Verbindung angefragt",
                                    "1033": "Connection requested"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "accepted",
                                "displayNames": {
                                    "1031": "Verbindung akzeptieren",
                                    "1033": "Accept connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "declined",
                                "displayNames": {
                                    "1031": "Verbindung ablehnen",
                                    "1033": "Decline connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "established",
                                "displayNames": {
                                    "1031": "Verbunden",
                                    "1033": "Established"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        },
        {
            "key": "updateNonLocalized",
            "displayNames": {
                "1031": "ElementType.UpdateNonLocalized",
                "1033": "ElementType.UpdateNonLocalized"
            },
            "descriptions": {
                "1031": "",
                "1033": ""
            },
            "properties": [
                {
                    "key": "name",
                    "displayNames": {
                        "1031": "Name",
                        "1033": "Name"
                    },
                    "descriptions": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "tooltips": {
                        "1031": "Name des Elements.",
                        "1033": "Name of element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "MultiLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "variantName",
                    "displayNames": {
                        "1031": "Variante",
                        "1033": "Variant"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "",
                        "1033": ""
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "SingleLineText",
                        "isInvariantCulture": false
                    }
                },
                {
                    "key": "state1",
                    "displayNames": {
                        "1031": "Status",
                        "1033": "State"
                    },
                    "descriptions": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's lifecycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1805.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "key": "inProcess",
                                "displayNames": {
                                    "1031": "In Bearbeitung",
                                    "1033": "In process"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "inReview",
                                "displayNames": {
                                    "1031": "In Review",
                                    "1033": "In review"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForQa",
                                "displayNames": {
                                    "1031": "Fertig für QA",
                                    "1033": "Ready for QA"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "readyForRelease",
                                "displayNames": {
                                    "1031": "Fertig zur Freigabe",
                                    "1033": "Ready for release"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "released",
                                "displayNames": {
                                    "1031": "Freigegeben",
                                    "1033": "Released"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requestToExpire",
                                "displayNames": {
                                    "1031": "Antrag auf abgelaufen",
                                    "1033": "Request to expire"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "expired",
                                "displayNames": {
                                    "1031": "Abgelaufen",
                                    "1033": "Expired"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "show",
                                "displayNames": {
                                    "1031": "Anzeigen",
                                    "1033": "Show"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "hide",
                                "displayNames": {
                                    "1031": "Ausblenden",
                                    "1033": "Hide"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "new",
                                "displayNames": {
                                    "1031": "Neu",
                                    "1033": "New"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "disconnected",
                                "displayNames": {
                                    "1031": "Nicht verbunden",
                                    "1033": "Disconnected"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requesting",
                                "displayNames": {
                                    "1031": "Verbindung anfragen",
                                    "1033": "Request connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "requested",
                                "displayNames": {
                                    "1031": "Verbindung angefragt",
                                    "1033": "Connection requested"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "accepted",
                                "displayNames": {
                                    "1031": "Verbindung akzeptieren",
                                    "1033": "Accept connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "declined",
                                "displayNames": {
                                    "1031": "Verbindung ablehnen",
                                    "1033": "Decline connection"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            },
                            {
                                "key": "established",
                                "displayNames": {
                                    "1031": "Verbunden",
                                    "1033": "Established"
                                },
                                "descriptions": {
                                    "1031": "",
                                    "1033": ""
                                },
                                "tooltips": {
                                    "1031": "",
                                    "1033": ""
                                }
                            }
                        ]
                    }
                },
                {
                    "key": "author",
                    "displayNames": {
                        "1031": "Autor",
                        "1033": "Author"
                    },
                    "descriptions": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "tooltips": {
                        "1031": "Der Benutzer, der die Elementbeschreibung erstellt oder betreut.",
                        "1033": "The user, who creates or cares for the element description."
                    },
                    "related": {
                        "relatedTypes": [],
                        "canAddNew": false,
                        "maxOccurrence": 1,
                        "readOnly": false,
                        "facet": "users"
                    }
                },
                {
                    "key": "description",
                    "displayNames": {
                        "1031": "Beschreibung",
                        "1033": "Description"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Zusätzlicher Beschreibungstext des Elements.",
                        "1033": "Additional description text of the current element."
                    },
                    "attribute": {
                        "type": "System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089",
                        "dataType": "Html",
                        "isInvariantCulture": false
                    }
                }
            ]
        }
    ]
}
```

## Definitions

### Type
{!developer/rest-api/reference/models/type.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
