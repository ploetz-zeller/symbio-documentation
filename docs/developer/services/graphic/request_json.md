# Request JSON
The request JSON is used for the **CalculateLayout** endpoint of the *Symbio-Graphic-Service*. Layout calculation can be requested for
* the calculation type <code>cxn</code> (connection) and
* the calculation type <code>flow</code> (process flow).

**Disclaimer:** The following comparison between the *request JSON* and *BPMN* is made not because the two formats perform a similar task, but because they convey similar content: **Process flows**.<br/><br/>
While the *request JSON* contains only the necessary information for automatic layout calculation and rendering, the BPMN also already contains all information for rendering - like position and size of shapes or the interpolation points of edges.

**BPMN sample for position and size of a shape**
```
<bpmndi:BPMNShape id="IntermediateThrowEvent_0iyvpzm_di" bpmnElement="IntermediateThrowEvent_0iyvpzm">
  <dc:Bounds x="458" y="313" width="36" height="36" />
  <bpmndi:BPMNLabel>
    <dc:Bounds x="464" y="353" width="24" height="12" />
  </bpmndi:BPMNLabel>
</bpmndi:BPMNShape>
```

**BPMN sample for interpolation points of an edge**
```
<bpmndi:BPMNEdge id="SequenceFlow_1vmk1br_di" bpmnElement="SequenceFlow_1vmk1br">
  <di:waypoint xsi:type="dc:Point" x="209" y="331" />
  <di:waypoint xsi:type="dc:Point" x="245" y="331" />
  <bpmndi:BPMNLabel>
    <dc:Bounds x="182" y="310" width="90" height="12" />
  </bpmndi:BPMNLabel>
</bpmndi:BPMNEdge>
```

## General structure
<table>
<tr><th>The file structure</th><th>Compared to BPMN</th><th>Comments</th></tr>
<tr>
<td>

```
{
    "result": "sesvg",
    "calculation": "flow",
    "configurations": [{
	...
    }],
    "elements": [{
	...
    }]
}
```

</td>
<td>

```

	



<bpmn:definitions> 
    ...
</bpmn:definitions>
```

</td>
<td>
The JSON format has to support layout and rendering requests for multiple purposes (<code>cxn</code> and <code>flow</code>) as well as multiple configurations.
<br/>
Thus it provides some meta-information like the requested  <b>"result"</b>, the type of  <b>"calculation"</b> to apply and details regarding layout and rendering configurations <b>"configurations"</b>.<br/>
Besides that, the JSON holds the data in the <b>"elements"</b> property just like the BPMN does it in the <b>&lt;bpmn:definitions/&gt;</b> tag.
</td>
</tr>
</table>

## The <code>result</code> property
The supported *result* types are:
1. <code>sesvg</code> (standalone enriched SVG) - used in case the resulting SVG has to be embedded into a custom HTML page and log messages are desired
2. <code>ssvg</code> (standalone SVG) - used in case the resulting SVG has to be embedded into a custom HTML page and log messages are not desired
3. <code>esvg</code> (HTML embedded enriched SVG) - used in case the resulting HTML has to be displayed directly (e. g. in a test app) and log messages are desired
4. <code>svg</code> (HTML embedded SVG) - used in case the resulting HTML has to be displayed directly (e. g. in a test app) and log messages are not desired
5. <code>ejson</code> (enriched JSON) - used in case the resulting JSON should be parsed to post-process the calculation result and log messages are desired
6. <code>json</code> (JSON) - used in case the resulting JSON should be parsed to post-process the calculation result and log messages are not desired

## The <code>calculation</code> property
The supported *calculation* types are:
* <code>cxn</code> (connection) - used to calculate a shape-to-shape connection
* <code>flow</code> (process flow) - used to calculate a directed graph, that represents a process flow

The *calculation* type <code>cxn</code> supports all *result* types.<br/>
The *calculation* type <code>flow</code> supports the *result* types 1. ... 4. only.

## The <code>configurations</code> property

*To be done.*

## The <code>elements</code> property

The <code>elements</code> property contains all elements, that make up a diagram. This includes:

- The **diagram** itself - as the container of all **shapes**.
  - All structure building **shapes** (and their edges), that are to be displayed within the *diagram*.
- The **items**, that are the basis to the **shapes**.

The <code>elements</code> property is designed to hold an *array* of elements.

It is recommended that the **diagram** is the first element within the array and the **items** are the elements following the **diagram** in the array. The **shapes** are included in the **diagram**.

<table>
<tr><th>The request JSON <i>elements</i> property</th><th>Compared to the BPMN <i>&lt;bpmn:definitions/&gt;</i> tag</th><th>Comments</th></tr>
<tr>
<td>

```
[{
  "id":
    "e8b07127331a4bae8135c5c8af381b12",
  "properties": {
    "type": "subProcess"
  },
  "attributes": [{
    "key": "name",
    "values": [
        { "lcid": 1033,
          "value": "Sub process" }
    ]
  }],
  "content": [
...
```
</td>
<td>

```
<bpmndi:BPMNDiagram
 id="BPMNDiagram_1">
  ...









  <bpmndi:BPMNPlane
   id="BPMNPlane_1"
   bpmnElement=
     "Collaboration_0q51prl">
  ...
```
</td>
<td>
&#x25B6; The <b>first</b> bunch of data in the request JSON file should be the <b>diagram</b>. It can be recognized by the fact that its <b><i>"type"</i></b> is <b><i>"subProcess"</i></b>.<br/>
The request JSON <b><i>diagram</i></b> typically contains also <b><i>attributes</i></b> while the BPMN <b><i>diagram</i></b> typically doesn't.<br/><br/>
The BPMN <b><i>diagram</i></b> might contain a <b><i>lane</i></b> node as primary child node of the <b><i>diagram</i></b> node.<br/><br/><br/>
</td>
</tr>
<tr>
<td>

```
    {
      "id":
        "a6743dd3-8881-4d22-bfe7-0b7f703097c8",
      "properties": {
        "itemId":
          "9bc5994a-f64f-431f-a631-1ff405f22643",
        "type":
          "evStart",
        "poolId":
          "b0907b38-e8e4-42f3-bc0a-d3e83ae2a1a7"
      }
    },
    ...






```

</td>
<td>

```
    <bpmndi:BPMNShape
     id="StartEvent_0034tgy_di"
       bpmnElement=
         "StartEvent_0034tgy">
      <dc:Bounds
       x="178" y="635"
       width="36" height="36" />
      <bpmndi:BPMNLabel>
        <dc:Bounds
         x="196" y="675"
         width="0" height="12"
      />
      </bpmndi:BPMNLabel>
    </bpmndi:BPMNShape>
    ...
```
</td>
<td>
Both, the request JSON <b><i>diagram</i></b> within the <b><i>content</i></b> property and the BPMN <b><i>diagram</i></b> within child nodes, contain the <b><i>shapes</i></b> and <b><i>edges</i></b> that are to be displayed.<br/><br/>
&#x25B6; The <b>second</b> bunch of data in the request JSON file should be the sequence of <b><i>shapes</i></b> within the <b><i>content</i></b> property of the <b></i>diagram</i></b>. The list of <b><i>shapes</i></b> should contain all structure building <b><i>shapes</i></b> to display.<br/><br/>
</td>
</tr>
<tr>
<td>

```
    {
      "id":
        "a6743dd3-8881-4d22-bfe7-0b7f703097c8",
      "properties": {
        "itemId":
          "9bc5994a-f64f-431f-a631-1ff405f22643",
        "sourceId":
          "a6743dd3-8881-4d22-bfe7-0b7f703097c8",
        "targetId":
          "75397704-e829-49b3-a40c-02379fb0b393",
        "type":
          "activ1",
        "poolId":
          "b0907b38-e8e4-42f3-bc0a-d3e83ae2a1a7"
      }
    },
    ...








    ],
  },
...
```
</td>
<td>

```
    <bpmndi:BPMNEdge
     id="SequenceFlow_0pern26_di"
     bpmnElement=
       "SequenceFlow_0pern26">
      <di:waypoint
       xsi:type="dc:Point"
       x="214" y="653"
      />
      <di:waypoint
       xsi:type="dc:Point"
       x="245" y="653"
      />
      <bpmndi:BPMNLabel>
        <dc:Bounds
         x="229.5" y="632"
         width="0" height="12" />
      </bpmndi:BPMNLabel>
    </bpmndi:BPMNEdge>
    ...
  </bpmndi:BPMNPlane>
</bpmndi:BPMNDiagram>
  ...
```

</td>
<td>
&#x25B6; The <b>third</b> bunch of data in the request JSON file should be the sequence of <b><i>edges</i></b> within the <b><i>content</i></b> property of the <b></i>diagram</i></b>. The list of <b><i>edges</i></b> should contain all <b><i>edges</i></b> to display. <br/><br/>
The following applies to both <b><i>shapes</i></b> and <b><i>edges</i></b>:<br/>
Both, the request JSON <b><i>shapes</i></b>/<b><i>edges</i></b> and the BPMN <b><i>shapes</i></b>/<b><i>edges</i></b>, provide an identifier <code>"id:"</code> (for request JSON) or <code>id</code> (for BPMN).
While the <code>itemId:</code> (for request JSON) refers to the underlying item id, as <code>id:</code> for <code>bpmnElement</code>, the <code>sourceId:</code> and <code>targetId:</code> hold the <code>id</code> of the connected shapes, as they are stated in the <b><i>diagram</i></b>'s <b><i>content</i></b> section.<br/><br/>
</td>
</tr>
<tr>
<td>

```
  {
    "id":
      "b0907b38-e8e4-42f3-bc0a-d3e83ae2a1a7",
    "properties": {
      "type": "pool",
      "kind": "OBJ",
      "servity": "source"
    },
    "attributes": [{
      "key": "name",
      "values": [
        { "lcid": 1033,
          "value": "Data source" }
      ]
    }]
  },
  ...


```
</td>
<td>

```
<bpmn:collaboration
 id="Collaboration_0q51prl">
  <bpmn:participant
   name="Data source"
   id="Participant_0zj6ka6"
   processRef="Process_0g17fhl"
  />
    ...
</bpmn:collaboration>










```

</td>
<td>
&#x25B6; The <b>fourth</b> bunch of data in the request JSON file should be the sequence of <b><i>pools</i></b> within the <b><i>elements</i></b> property of the request JSON (the <b><i>diagram</i></b> property has been finished already at this point). The list of <b><i>pools</i></b> should contain all <b><i>pools</i></b> that are used to hold <b><i>lanes</i></b> or <b><i>shapes</i></b>.<br/><br/>
Both, the request JSON <b><i>pools</i></b> and the BPMN <b><i>participants</i></b>, provide an identifier <code>"id:"</code> (for request JSON) or <code>id</code> (for BPMN) and a name <code>"key": "name"</code> (object within the <code>"attributes"</code> property for request JSON) or <code>name</code><br/> (for BPMN).
</td>
</tr>
<tr>
<td>

```
  {
    "id":
      "B63F2971E571B69F49AAD5B0733302FA",
    "properties": {
      "type": "evStart",
      "kind": "OBJ",
      "evType": "throwSignal"
    },
    "attributes": [{
      "key": "name",
      "values": [
        { "lcid": 1033,
          "value": "Start" }
      ]
    }]
  },
  ...
]
```

</td>
<td>

```
<bpmn:process
 id="Process_0g17fhl"
 isExecutable="false">
  <bpmn:startEvent
   id="StartEvent_0034tgy">
    <bpmn:outgoing>
      SequenceFlow_0pern26
    </bpmn:outgoing>
  </bpmn:startEvent>
  ...







```

</td>
<td>
&#x25B6; The <b>fifth</b> bunch of data in the request JSON file should be the sequence of shape <b><i>items</i></b>, referenced by <b><i>shapes</i></b>.<br/><br/>
Both, the request JSON <b><i>items</i></b> and the BPMN <b><i>process</i></b> child nodes, provide an identifier <code>"id:"</code> (for request JSON) or <code>id</code> (for BPMN).<br/><br/><br/><br/><br/><br/>
</td>
</tr>
<tr>
<td>

```
  {
    "id":
      "D4B07549771B2932CFEE51B63969502F",
    "properties": {
      "type": "activ1",
      "kind": "CXN"
    },
    "attributes": [{
      "key": "cxnRole",
      "values": [
        { "lcid": 1033,
          "value": "01" }
      ]
    }]
  },
  ...
]
```

</td>
<td>

```
  <bpmn:sequenceFlow
   id="SequenceFlow_0pern26"
   sourceRef="StartEvent_0034tgy"
   targetRef="Task_1di8scb"
  />
  ...










</bpmn:process>
```

</td>
<td>
&#x25B6; The <b>sixth</b> bunch of data in the request JSON file should be the sequence of connection <b><i>items</i></b>, referenced by <b><i>edges</i></b>.<br/><br/>
Both, the request JSON connection <b><i>items</i></b> and the BPMN <b><i>process</i></b> child nodes, provide an identifier <code>"id:"</code> (for request JSON) or <code>id</code> (for BPMN).<br/><br/><br/><br/>
</td>
</tr>
</table>

### Shapes and shape items
The design of ***shape*** content elements is intended to be minimalistic.<br/>

```
{
	"id": "a6743dd3-8881-4d22-bfe7-0b7f703097c8",
	"properties": {
            "itemId": "9bc5994a-f64f-431f-a631-1ff405f22643",
            "type": "evStart",
            "poolId": "6496cb0f-8763-4e27-a8dd-77870be94fd5"
	}
}
```

Referencing the ***shape***'s underlying ***item*** is done with <code>"itemId" : "9bc5994a-f64f-431f-a631-1ff405f22643"</code>.<br/>
The (optional) second reference, <code>"poolId": "6496cb0f-8763-4e27-a8dd-77870be94fd5"</code>, defines membership of the ***shape*** in a ***pool***.<br/>
<br/>

Here is the ***shape*** underlying ***item***:

```
{
  "id": "9bc5994a-f64f-431f-a631-1ff405f22643",
  "properties": {
    "type": "evStart",
    "kind": "OBJ",
    "evType": "throwSignal"
  },
  "attributes": [{
    "key": "name",
    "values": [
      { "lcid": 1033, "value": "recognize hunger" }
    ]
  }]
}
```

The ***type*** is provided via the <code>"properties"</code> property array property <code>"type"</code>.<br/>
In addition to that the kind (which determines whether it is a ***shape*** or a ***edge***) is provided via the <code>"properties"</code> property array property <code>"kind"</code>.<br/>
In case the ***item*** (and thus the ***shape*** as well) is defined more specifically, the <code>"properties"</code> property array might contain a property <code>"evType"</code> or <code>"funcType"</code> ore <code>"funcMarker"</code>.<br/>
The text to display is defined within the <code>"attributes"</code> property array object with the <code>"key": "name"</code>. Since the request JSON supports multiple languages, the name value is provided by the <code>"values"</code> property array, that can hold distinct value objects for different cultures.

### Edges and edge items
The design of ***edge*** content elements is intended to be minimalistic.<br/>
Here is an example:

```
{
	"id": "e5dfd46e-8720-408e-b760-171038da9f6d",
	"properties": {
		"itemId": "6496cb0f-8763-4e27-a8dd-77870be94fd5",
		"sourceId": "a6743dd3-8881-4d22-bfe7-0b7f703097c8",
		"targetId": "75397704-e829-49b3-a40c-02379fb0b393",
		"type": "activ1"
	}
}
```

Referencing the ***edge***'s underlying ***item*** is done with <code>"itemId" : "6496cb0f-8763-4e27-a8dd-77870be94fd5"</code>.<br/>
The is no reference to a ***pool***, since ***edges*** can cross ***lanes*** and ***pools***.<br/>
The referencing of the *source* and *target* ***shapes*** is done with <code>"sourceId": "a6743dd3-8881-4d22-bfe7-0b7f703097c8"</code> and <code>"targetId": "75397704-e829-49b3-a40c-02379fb0b393"</code>. An ***edge*** must always hold a *source* and a *target* ***shape*** reference.<br/><br/>

Here is the ***edge*** underlying ***item***:

```
{
    "id": "6496cb0f-8763-4e27-a8dd-77870be94fd5",
    "properties": {
        "kind": "CXN",
        "sourceId": "9bc5994a-f64f-431f-a631-1ff405f22643",
        "targetId": "b0907b38-e8e4-42f3-bc0a-d3e83ae2a1a7",
        "type": "activ1"
	},
    "attributes": [{
        "key": "cxnRole",
        "values": [
        { "lcid": 1033, "value": "yes" }
        ]
    }]
}
```

The ***type*** is provided via the <code>"properties"</code> property array property <code>"type"</code>.<br/>
In addition to that the kind (which determines whether it is a ***shape*** or a ***edge***) is provided via the <code>"properties"</code> property array property <code>"kind"</code>.<br/>
The text to display is defined within the <code>"attributes"</code> property array object with the <code>"key": "cxnRole"</code>. Since the request JSON supports multiple languages, the name value is provided by the <code>"values"</code> property array, that can hold distinct value objects for different cultures.

### Pool items
In the case that the **diagram** is to be laid out and rendered with **pools**, the **pools** *should* be the first **items** and *must* be contained in the order in which they are expected in the final layout/rendering. This is an exoample with three **pools**:

```
{
	"id": "d5d7ce44-c18f-4119-aa18-8f9e8aa69e85",
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
	"id": "03c092c9-b723-4a38-befd-f6f54aef42d6",
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
		"467cbfa4-ff43-49fe-ac0d-49beda2e07f6",
		"c989af38-3e9e-4693-a284-3801da7696de"
	]
},
{
	"id": "63cf252b-ed7f-458e-97c3-3b557786eb52",
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

### Lane items
In the case that the **diagram** is to be laid out and rendered with **lanes**, the **lanes** are *automatically* recognized by the fact, that they are *related* to structure building  **items** via the configured *laneRelevant* relation (see <code>"laneRelevant": "responsible"</code> within **<code>configurations</code> property**). The  **lanes** must not be of any of any specific **item** type (see <code>"type": "..."</code>), but they must be of **item** kind "OBJ" (see <code>"kind": "OBJ"</code>) and must not be of any of the structure building  **item** types (like <code>"type": "func"</code>, <code>"type": "evStart"</code>, <code>"type": "evIntermediate"</code>, <code>"type": "evEnd"</code>, <code>"type": "ruleXor"</code>, <code>"type": "ruleOr"</code>, <code>"type": "ruleAnd"</code> or <code>"type": "condition"</code>).

In the case that multiple **lanes** should be contained in a **pool** and the **lanes** should be in a defined order, it is recommended to define the **lanes** as a list of children (see <code>"children"</code>) within the **pool**. The **ids**, specified in the list of children, must refer to existing **lane** (**items**), that are typically *roles*, *groups*, *application systems* or *application services*.
