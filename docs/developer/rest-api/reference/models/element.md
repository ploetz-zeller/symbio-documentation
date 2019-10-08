| Name | Type | Description |
|---|---|---|
| id | Guid? | The identifier of the element. |
| versionId | Guid? | The identifier of the specific version. |
| state | string | The current state of the element. |
| stereotype | string | The stereotype of the element. |
| type | string | The type of the element. |
| attributes | Dictionary&lt;string, Dictionary&lt;int, object&gt;&gt; | The attributes of the element. |
| related | Dictionary&lt;string, List&lt;Element&gt;&gt; | The list of related elements. |
| children | Element[] | The list of child elements. |
| content | Element[] | The list of content elements. |
| rootPath | Element[] | The list of hierarchical parent elements to the root element. |
| displayNames | Dictionary&lt;int, string&gt; | Gets the display names of multiple languages. |
| expandUri | string | Gets or sets the expand Uri to get full information about element |
| facetName | string | Name of the facet |
| setReadOnly | bool? | Gets or sets the read only of the element |
| versions | Element[] | Element versions of this container |