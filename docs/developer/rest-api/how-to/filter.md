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
