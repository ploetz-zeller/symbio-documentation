
| Status: March 2019   | ©2019 Ploetz + Zeller GmbH   |
|--------------------|------------------------------|

# Symbio API Filter

Filters can be part of the Uri and cause the server to return a filtered amount of data. For example, you can query all elements with a specific name specified in the filter.

## Syntax

The filters are part of the Uri.
```
https://Server/Collection/Database/_api/rest/facets/processes/views/tree/elements/Origin Key of Category?$filter=name -eq 'mainProcess'
```
## Type of filters / operations

### Binary Operators

| Name | Syntax | Type | Description | Example |
|---|---|---|---|---|
| Equal | -eq | string | The Boolean equality operator. | ?$filter=name -eq string |

### Function Operators

| Name | Syntax | Type | Description | Example |
|---|---|---|---|---|
| Contains | Contains(string to be searched, substring to search) | string | Determines if one string occurs within another string. | ?$filter=contains(attributes, 'test') |
| EndsWith | EndsWith(string to be searched, substring to search at the end of the first string) | string | Determines if the end of one string matches another string. | ?$filter=EndsWith(attributes, 'test') |
| StartsWith | StartsWith(string to be searched, substring to search at the beginning of the first string) | string |Determines if the beginning of one string matches another string. | ?$filter=StartsWith(attributes, 'test') |
| IsNull | IsNull(key to check for null) | string | Compares the first operand with the null value. Compares if value null, empty or whitespace. | ?$filter=IsNull(attributes) |

### Operator Error

If you use an invalid filter operant, you get either a code 404 for an invalid uri or a hint that this operator is not implemented.
```json
{
    "data": [
        {
            "error": "The operator Custom is currently not supported"
        }
    ],
    "message": "An error occurred.",
    "output": "Volatile",
    "type": "Error"
}
```
## Queries

It is possible to create a query in which filters are used in combination. An example in which the value'mainprocess' in the `name` attribute is filtered and the value in the `sate1` attribute does not correspond to'in progress'.

| Name | Syntax | Type | Description | Example |
|---|---|---|---|---|
| And | AND | string | Groups operands with logical AND | ?$filter=name Equal string AND state1 Equal string  |
| Or | OR | string | Groups operands with logical OR.	 | ?$filter=name Equal string OR state1 Equal string |

### Query example
```
https://Server/Collection/Database/_api/rest/facets/processes/views/tree/elements/Origin Key of Category?$filter=name -eq 'mainProcess' AND state1 -eq 'in progress'
```

Other combinations are also possible.

# FAQ's

More information about the correct construction of the uri's can be found here:
[API References](xref:refrenceindex)

Impressum
=======================================================================================================

 **publisher**

 Ploetz + Zeller GmbH

 Einsteinring 41-43

 85609 München

 Tel.: +49 89 890635 – 0

 Fax: +49 89 890635 – 55

 E-Mail: info@p-und-z.de  |
|-------------------------|

| **IMPRESSUM**                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---|
|
Ploetz + Zeller GmbH accepts no liability for the correctness and completeness of the presentation/image in the document. The described and possible functionalities of the software refer to the respective version status. Customer-specific adaptations are not included. The information in this document is subject to change at any time. Ploetz + Zeller GmbH is not obliged to inform about the updates of the document.


 This documentation as well as all contributions, representations and illustrations contained therein are protected by copyright. Any use not expressly permitted by copyright law requires the prior consent of Ploetz + Zeller GmbH. This applies in particular to reproductions, adaptations, translations, microfilming as well as storage and processing in electronic systems.

 Ploetz + Zeller GmbH regards the information, knowledge and illustrations contained in this documentation as its sole property. The documentation or the information, knowledge and illustrations contained therein may not be made available, published or otherwise disseminated to third parties, either in whole or in part, directly or indirectly, without the prior written consent of Ploetz + Zeller GmbH.
                                                                                                                                                                                                                                                                                                                                                                                                         Ploetz + Zeller GmbH reserves the right to assert all relevant rights, in particular in the event of patents being granted. The handing over of the documentation does not create any claim to a license or use.

 Subject to technical modifications. Product names used are trademarks or registered trademarks of their respective owners.

 Symbio® is a registered trademark of PLOETZ + ZELLER GmbH, Munich.                                                                                                                                                                                                                                                                                                                                                                                                     |


| Ploetz + Zeller GmbH

 Einsteinring 41-43

 85609 München                                              |
| Phone: +49 89 890635 – 0

 Fax: +49 89 890635 – 55

 E-Mail: <info@p-und-z.de>

 ©2018 Ploetz + Zeller GmbH                                 |

