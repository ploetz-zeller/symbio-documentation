# Request JSON

## General structure

<code>{</code><br />
<code>&nbsp;&nbsp;"result": "sesvg",</code><br />
<code>&nbsp;&nbsp;"calculation": "flow",</code><br />
<code>&nbsp;&nbsp;"cfg": [{</code><br />
<code>&nbsp;&nbsp;&nbsp;&nbsp;...</code><br />
<code>&nbsp;&nbsp;}],</code><br />
<code>&nbsp;&nbsp;"elements": [{</code><br />
<code>&nbsp;&nbsp;&nbsp;&nbsp;...</code><br />
<code>&nbsp;&nbsp;}]
}</code>

## The <code>result</code> property

*To be done.*

## The <code>calculation</code> property

*To be done.*

## The <code>cfg</code> property

*To be done.*

## The <code>elements</code> property

The <code>elements</code> property contains all elements, that make up a diagram. This includes:

- The **diagram** itself - as the container of all **shapes**.
  - All **shapes**, that are to be displayed within the *diagram*.
- The **items**, that are the basis to the **shapes**

The <code>elements</code> property is designed to hold an *array* of elements.

It is recommended that the **diagram** is the first element within the array and the **items** are the elements following the **diagram** in the array. The **shapes** are included in the **diagram**.

## Pool items
In the case that the **diagram** is to be laid out and rendered with **pools**, the **pools** *should* be the first **items** and *must* be contained in the order in which they are expected in the final layout/rendering. This is an exoample with three **pools**:

```
{
	"id": "CCA71B63D5B0733302E571B69F49BB32",
	"properties": {
		"type": "pool",
		"kind": "OBJ",
		"servity": "source"
	},
	"attributes": [{
		"key": "name",
		"values": [
			{ "lcid": 1033, "value": "Data source" }
		]
	}]
},
{
	"id": "AAA71B63D5B0733302E571B69F4CCC",
	"properties": {
		"type": "pool",
		"kind": "OBJ"
	},
	"attributes": [{
		"key": "name",
		"values": [
			{ "lcid": 1033, "value": "Processing" }
		]
	}],
	"children": [
		"D886BBB12CE11D664AEF9197FA08B97D",
		"2CE1AAA11A664ADF9197FB08B97DD886"
	]
},
{
	"id": "C1271B63D5B0733302E571B69F4AAF",
	"properties": {
		"type": "pool",
		"kind": "OBJ",
		"servity": "target"
	},
	"attributes": [{
		"key": "name",
		"values": [
			{ "lcid": 1033, "value": "Data target" }
		]
	}]
},
...
```
It must be designated that the **pools** are of **item** type "pool" (see <code>"type": "pool"</code>) and of **item** kind "OBJ" (see <code>"kind": "OBJ"</code>). One **pool** should be designated as the default **pool** so that **shapes** can be attached to the default **pool** without explicitly assigning a **pool** to **shapes**. This creates a fail-safe and makes the JSON code shorter. To identify the default **pool** you can:

- Mark all **pools** except the default **pool** as "source" (see <code>"servity": "source"</code>) or "target" (see <code>"servity": "target"</code>). In case of multiple matches, the last one wins.
- Mark the default **pool** (see <code>"servity": "default"</code>). In case of multiple matches, the last one wins.
- In case no pool is designated as the default **pool**, the centre **pool** (count / 2) is used.

It is highly recommended to define names for all **pools** (see <code>"attributes"</code> with <code>"key": "name"</code>).

In the case that a **pool** should contain multiple **lanes** and the **lanes** should be in a defined order, it is recommended to define the **lanes** as a list of children (see <code>"children"</code>). The **ids**, specified in the list of children, must refer to existing **items**, that are typically *roles*, *groups*, *application systems* or *application services*.
