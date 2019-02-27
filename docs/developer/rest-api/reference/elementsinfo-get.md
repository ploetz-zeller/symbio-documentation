---
uid: attributesinfoget
---
# Element information

**api-version**: 1.0

Retrieves information for a specific element.

```
POST /{collectionId}/{storageId}/_api/rest/facets/{facetId}/views/{viewId}/elements/{elementId}/info
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
| values | [ElementInfo[]](#elementinfo) | The list of element information. |

#### ElementInfo

| Name | Type | Description |
|---|---|---|
| id | string | The ID of the element. |
| elementTypeName | string | The name of the element type. |
| entityIds | string[] | All identifier of mapped entities and shapes. |
| hasDiagram | bool | Gets a value indicating whether this instance has a diagram. |
| hasEditPermission | bool | Gets a value indicating whether this element has edit permission. |
| insertableDynamicTypes | string[] | Gets the dynamic insertable types, i.e., the types that depend on the current element. |
| isCurrentCopyable | bool | Gets a value indicating whether this element is copyable. |
| isCurrentInsertable | bool | Gets a value indicating new elements can be inserted on this element. |
| isCurrentMovable | bool | Gets a value indicating whether this instance is current movable. |
| isCurrentRemovable | bool | Gets a value indicating whether this instance is removable. |
| isReadOnly | bool | Gets a value indicating whether this element is read only. |
| isReadOnlyCollection | bool | Gets a value indicating whether the collection in this element is read only. |
| name | string | The name of the element. |
| readOnlyCollectionContext | None &#124; Diagram &#124; Architect &#124; All &#124; NotCurrentUser &#124; Never | Gets the read only collection context. |
| readOnlyContext | None &#124; Diagram &#124; Architect &#124; All &#124; NotCurrentUser &#124; Never | Gets the read only context. |
| rootPath | string[] | Gets the root path. |
| shapeId | string | Gets the shape identifier. |
| typeColor | string | Gets the color of the type. |
| uid | string | Gets an unique identifier based on parent element, e.g. "\_[id]" for a flat view or "[parent_id]_[id]" for a hierarchical view. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the element information

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views/detail/elements/168c8bc4-779e-4697-8334-0026411d52f1/info
```

#### Reponse (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "elementTypeName": "SubCategory",
            "entityIds": [
                "4d70ccc4-e822-4496-a4f0-7ff24386f168",
                "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
                "e02eef7c-f7e1-419d-83ff-48b7bef71c7f"
            ],
            "entityTypeName": "MTX_SUB_CATEGORY",
            "facetTypeName": "Processes",
            "hasDiagram": true,
            "hasEditPermission": false,
            "id": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
            "insertableDynamicTypes": {},
            "isCurrentCopyable": false,
            "isCurrentInsertable": false,
            "isCurrentMovable": true,
            "isCurrentRemovable": false,
            "isReadOnly": true,
            "isReadOnlyCollection": true,
            "name": "Managementprozesse",
            "readOnlyCollectionContext": "Diagram",
            "readOnlyContext": "None",
            "rootPath": [
                "20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
            ],
            "shapeId": "20e369c5-f0f8-491b-9e7f-f15db6a0fb80",
            "typeColor": "",
            "uid": "_20e369c5-f0f8-491b-9e7f-f15db6a0fb80"
        }
    ]
}
```

## Definitions

### ElementInfo
[!include[](models\element.md)]

### OperationResultType 
[!include[](models\operationresulttype.md)]

### Error
[!include[](models\error.md)]
