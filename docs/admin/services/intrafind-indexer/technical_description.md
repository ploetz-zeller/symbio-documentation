# Technical description of fields used in Intrafind documents for internal use

## How are Intrafind documents constructed

Each document consists of a globally unique identifier named 'id' containing a string value, and a property named 'fields' containing a collection of key-value pairs with a string as a key and a string collection as the value.
You can add any kind of key-value pairs to the fields collection, but you have to add some mandatory field entries listed below to enable Intrafind to make proper use of the indexed documents and to be able to find information in its context.

Keep in mind: When a new document uses an already defined identifier, this new document will overwrite the existing document without any notice.
Updating an existing document means, you have to send all the data belonging to the document, not only the changed parts of it. There are no Change-/Update-commands defined.


### Document structure

    {
        "id": "<unique id>",
        "fields": [
            { "_str.title": { "Test document" } },
            { "_str.body": { "Lorem ipsum", "123", "and so on..." } },
            ...
        ]
    }

### Mandatory fields by Intrafind

| Field             | Description |
| ---               | --- |
| _str.title        | name of document |
| _str.body         | all content will be indexed, so if you want to have the symbio attributes 'name' and 'description' to be indexed, you have to add their content strings to this field |
| _str.connector    | always the constant value 'symbio' |
| _raw.tenant       | configurable value to distinguish sources of indexed documents in Intrafind |
| _str.application  | 'HTML' for all Symbio objects |
| _str.mimetype     | 'html' and 'xhtml' for all Symbio objects |
| _str.url          | Deep-Link to Symbio object (GotoUrl-attribute) |

### Mandatory fields defined by Symbio

| Field             | Description |
| ---               | --- |
| _int.lcid         | Language of the document; like '1031' for german, or '1033' for english. This is a string value |
| _raw.tenantId     | Symbio-internal database instance |
| _str.scope        | either 'Viewer' or 'Editor' |
| _raw.versionId    | Symbio-internal version-specific identifier |
| _raw.containerId  | Symbio-internal identifier for the container element for the specified version |
| _raw.contentId    | Symbio-internal identifier to the content element (e.g., this Intrafind document references a 'task') |
_
### Technical fields defined by Symbio

| Field                    | Description |
| ---                      | --- |
| _str.symbio.type         | the element's type ('subProcess' e.g.) |
| _str.symbio.version      | the version as text string |
| _str.symbio.stereoType   | the stereotype of the element |
| _str.referencedDocuments | if the element contains external linked documents, this field would contain these links as a string collection |

### Further fields defined by 'Attribute Filter' in 'Custom External System Type'

All further fields defined in the 'Attribute Filter' are prefixed by '_str.symbio.'.

E.g.

-	‘_str.symbio.name’
-	‘_str.symbio.description’
-	‘_str.symbio.links’

and so on.

Documents which are created by Intrafind's 'ConvertLocation' API call contain an additional field named ‘_raw.originLink’ containing the 'GotoUrl' attribute's value as a back reference.

