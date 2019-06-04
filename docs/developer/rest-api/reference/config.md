# Configuration

**api-version**: 1.0

Retrieves the configuration of possible elements in a view.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/config/{type}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| facetId | path | true | string | The name of the facet. |
| viewId | path | true | string | The name of the view. |
| type | path | true | string | The name of element type. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [ElementType[]](#elementtype) | The list of element types. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| output | [OperationResultOutput](#operationresulttype) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the elements config by type from the *tree* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/config/processhouse
```

#### Response (200 OK)
```json
{
    "count": 1,
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
                    "key": "stereotype",
                    "displayNames": {
                        "1031": "Stereotyp",
                        "1033": "Stereotype"
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
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1906.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": []
                    }
                },
                {
                    "key": "version",
                    "displayNames": {
                        "1031": "Version",
                        "1033": "Version"
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
                        "isInvariantCulture": true
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
                        "1033": "Current phase of an element's life-cycle."
                    },
                    "tooltips": {
                        "1031": "Aktuelle Phase im Lebenszyklus eines Elements.",
                        "1033": "Current phase of an element's life-cycle."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1906.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": []
                    }
                },
                {
                    "key": "processMaturity",
                    "displayNames": {
                        "1031": "Reifegrad",
                        "1033": "Maturity"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Das Maß für den Erfüllungsgrad definierter Kriterien bezüglich Prozess-Qualität.",
                        "1033": "The measure for the degree of fulfillment of defined criteria regarding process quality."
                    },
                    "attribute": {
                        "type": "Symbio.Base.Framework.Method.ISelectableValue, Symbio.Base.Framework, Version=1906.0.0.0, Culture=neutral, PublicKeyToken=null",
                        "dataType": "SelectionValue",
                        "isInvariantCulture": true,
                        "selectableValues": [
                            {
                                "displayNames": {
                                    "1031": "Nicht relevant",
                                    "1033": "Not relevant"
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
                                "key": "defined",
                                "displayNames": {
                                    "1031": "10% - Prozess definiert",
                                    "1033": "10% - Process defined"
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
                                "key": "implemented",
                                "displayNames": {
                                    "1031": "30% - Prozess implementiert",
                                    "1033": "30% - Process implemented"
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
                                "key": "trained",
                                "displayNames": {
                                    "1031": "40% - Prozess geschult",
                                    "1033": "40% - Process trained"
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
                                "key": "isLived",
                                "displayNames": {
                                    "1031": "60% - Prozess wird gelebt",
                                    "1033": "60% - Process is lived"
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
                                "key": "isMeasured",
                                "displayNames": {
                                    "1031": "80% - Prozess wird gemessen",
                                    "1033": "80% - Process is measured"
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
                                "key": "getsImproved",
                                "displayNames": {
                                    "1031": "100% - Prozess wird kontinuierlich optimiert",
                                    "1033": "100% - Process get improved"
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
                    "key": "owner",
                    "displayNames": {
                        "1031": "Verantwortlich",
                        "1033": "Responsible"
                    },
                    "descriptions": {
                        "1031": "",
                        "1033": ""
                    },
                    "tooltips": {
                        "1031": "Üblicherweise gibt dieser Benutzer die Elementbeschreibung frei.",
                        "1033": "This user releases the element description."
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
            ],
            "layouts": [
                {
                    "key": "detailed",
                    "displayNames": {
                        "1031": "Detailliert",
                        "1033": "Detailed"
                    }
                },
                {
                    "key": "graphic",
                    "displayNames": {
                        "1031": "Grafik",
                        "1033": "Graphic"
                    }
                }
            ]
        }
    ]
}
```

### Get the elements config from the *tree* view of the *processes* facet

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/tree/config
```

#### Response (200 OK)
```json
The code is not displayed because over 50000 lines long.
```

### Get the configuration of the process graphic

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/diagram/config
```

#### Reponse (200 OK)
```json
{
    "count": 5,
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
                }
            ]
        }
    ]
}
```

## Definitions

### ElementType
{!developer/rest-api/reference/models/elementtype.md!}

### OperationResult
{!developer/rest-api/reference/models/operationresult.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
