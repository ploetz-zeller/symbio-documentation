
# SAP Solution Manager Connector - Set up custom attributes sync

This document contains information on how to configure synchronization of custom attributes between Symbio and SAP Solution Manager Connector.

The configuration of custom attributes is set in a JSON file, and can be set in the External System settings for the Solman external system.
The following information is needed:

- SAP Solution Manager attribute technical ID
- Symbio attribute id (**CASE SENSITIVE!!!**)
- Type of attribute (see types below)
- Is attribute language independent
- Symbio element types on which the custom attribute is activated
- For dropdown/multiselect/related attributes mapping of values and names is needed

The examples are given below.

## Text, Number, Bool and Date attributes

The given example represents how the structure should look for the following **types**:

- "singlelinetext"  
- "multilinetext"
- "int"
- "float"
- "date"
- "bool"

```json
{
  "customAttributeMappings": [
    {
      "solmanAttributeTechnicalId": "{SOLMAN_TECHNICAL_ID}",
      "symbioAttributeId": "{symbio_attribute_id}", //CASE SENSITIVE!!!
      "attributeType": "{type}",
      "isLanguageIndependent": true or false,
      "availableOn": [
        "{symbioElementTypes}"
      ]
    }
  ]
}
```

## Dropdown attribute

The given example represents how the structure should look for the **dropdown** attribute:

```json
{
  "customAttributeMappings": [
    {
      "solmanAttributeTechnicalId": "{SOLMAN_TECHNICAL_ID}",
      "symbioAttributeId": "{symbio_attribute_id}", //CASE SENSITIVE!!!
      "attributeType": "dropdown",
      "isLanguageIndependent": true or false,
      "availableOn": [
        "{symbioElementTypes}"
      ],
      "values": [
        {
          "value": "{customAttributeValue}",
          "name": [
            {
              "lcid": {int value for lcid},
              "nameValue": "{value}"
            }
          ]
        }
      ]
    }
  ]
}
```

## Multiselect attribute

The given example represents how the structure should look for the **multiselect** attribute:

```json
{
  "customAttributeMappings": [
    {
      "solmanAttributeTechnicalId": "{SOLMAN_TECHNICAL_ID}",
      "symbioAttributeId": "{symbio_attribute_id}", //CASE SENSITIVE!!!
      "attributeType": "multiselection",
      "isLanguageIndependent": true or false,
      "availableOn": [
        "{symbioElementTypes}"
      ],
      "values": [
        {
          "value": "{customAttributeValue1}",
          "name": [
            {
              "lcid": {int value for lcid},
              "nameValue": "{value}"
            }
          ]
        },
        {
          "value": "{customAttributeValue2}",
          "name": [
            {
              "lcid": {int value for lcid},
              "nameValue": "{value}"
            }
          ]
        }
      ]
    }
  ]
}
```

## Related attribute

The given example represents how the structure should look for the **related** elements attribute:

```json
{
  "customAttributeMappings": [
    {
      "solmanAttributeTechnicalId": "{SOLMAN_TECHNICAL_ID}",
      "symbioAttributeId": "{symbio_related_id}", //CASE SENSITIVE!!!
      "attributeType": "related",
      "isLanguageIndependent": true or false,
      "availableOn": [
        "{symbioElementTypes}"
      ],
      "values": [
        {
          "value": "{originKeyOfTheRelatedElementContainer1}",
          "name": [
            {
              "lcid": {int value for lcid},
              "nameValue": "{value}"
            }
          ]
        },
        {
          "value": "{originKeyOfTheRelatedElementContainer2}",
          "name": [
            {
              "lcid": {int value for lcid},
              "nameValue": "{value}"
            }
          ]
        }
      ]
    }
  ]
}
```