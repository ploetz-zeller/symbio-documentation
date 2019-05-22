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