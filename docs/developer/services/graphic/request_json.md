# Request JSON
The request JSON is used for the **CalculateLayout** endpoint of the *Symbio-Graphic-Service*. Layout calculation can be requested for
* the calculation type <code>cxn</code> (connection) and
* the calculation type <code>flow</code> (process flow).

**Disclaimer:** The following comparison between the *request JSON* and *BPMN* is made not because the two formats perform a similar task, but because they convey similar content: **process flows**<br/>
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

**BPMN sample forinterpolation points of an edge**
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
    "cfg": [{
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
Thus it provides some meta-information like the requested  <b>"result"</b>, the type of  <b>"calculation"</b> to apply and details regarding layout and rendering configuration <b>"cfg"</b>.<br/>
Beside taht, the JSON holds the data in the <b>"elements"</b> property just like the BPMN does it in the <b>&lt;bpmn:definitions/&gt;</b> tag.
</td>
</tr>
</table>

## The <code>result</code> property
The supported *result* types are:
1. <code>sesvg</code> (standalone enriched SVG) - used in case the resulting SVG hast to be embedded into a custom HTML page and log messages are desired
2. <code>ssvg</code> (standalone SVG) - used in case the resulting SVG hast to be embedded into a custom HTML page and log messages are not desired
3. <code>esvg</code> (HTML embedded enriched SVG) - used in case the resulting HTML hast to be displayed directly (e. g. in a test app) and log messages are desired
4. <code>svg</code> (HTML embedded SVG) - used in case the resulting HTML hast to be displayed directly (e. g. in a test app) and log messages are not desired
5. <code>ejson</code> (enriched JSON) - used in case the resulting JSON should be parsed to post-process the calculation result and log messages are desired
6. <code>json</code> (JSON) - used in case the resulting JSON should be parsed to post-process the calculation result and log messages are not desired

## The <code>calculation</code> property
The supported *calculation* types are:
* <code>cxn</code> (connection) - used to calculate a shape-to-shape connection
* <code>flow</code> (process flow) - used to calculate a directed graph, that represents a process flow

The *calculation* type <code>cxn</code> supports all *result* types.<br/>
The *calculation* type <code>flow</code> supports the *result* types 1. ... 4. only.

## The <code>cfg</code> property

*To be done.*

## The <code>elements</code> property

The <code>elements</code> property contains all elements, that make up a diagram. This includes:

- The **diagram** itself - as the container of all **shapes**.
  - All **shapes**, that are to be displayed within the *diagram*.
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
&#x25B6; <b>First</b> element in the request JSON file should be the <b>diagram</b>. It can be recognized by the fact that its <b><i>"type"</i></b> is <b><i>"subProcess"</i></b>.<br/>
The request JSON <b><i>diagram</i></b> typically contains also <b><i>attributes</i></b> while the BPMN <b><i>diagram</i></b> dypically doesn't.<br/><br/>
The BPMN <b><i>diagram</i></b> might contain a <b><i>lane</i></b> node as primary child node of the <b><i>diagram</i></b> node.<br/><br/><br/>
</td>
</tr>
<tr>
<td>

```
    {
      "id":
        "E571B6CA71B63D5B0733C3029F49BB32",
      "properties": {
        "itemId":
          "CCA71B63D5B0733302E571B69F49BB32"
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
&#x25B6; <b>Second</b> element in the request JSON file should be the list of <b><i>shapes</i></b> within the <b><i>content</i></b> property of the <b></i>diagram</i></b>. The list of <b><i>shapes</i></b> should contain all <b><i>shapes</i></b> to display.<br/><br/>
</td>
</tr>
<tr>
<td>

```
    {
      "id":
        "549FCE902F71B671BE5695B07CCA9FF2",
      "properties": {
        "itemId":
          "B63F2971E571B69F49AAD5B0733302FA",
        "poolId":
          "CCA71B63D5B0733302E571B69F49BB32"
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
&#x25B6; <b>Third</b> element in the request JSON file should be the list of <b><i>edges</i></b> within the <b><i>content</i></b> property of the <b></i>diagram</i></b>. The list of <b><i>edges</i></b> should contain all <b><i>edges</i></b> to display. <br/><br/>
The following applies to both <b><i>shapes</i></b> and <b><i>edges</i></b>:<br/>
Both, the request JSON <b><i>shapes</i></b>/<b><i>edges</i></b> and the BPMN <b><i>shapes</i></b>/<b><i>edges</i></b>, provide an identifier <code>"id:"</code> (for request JSON) or <code>id</code> (for BPMN) and areference to the underlaying item <code>"itemId:"</code> (for request JSON) or <code>bpmnElement</code><br/> (for BPMN).<br/><br/>
</td>
</tr>
<tr>
<td>

```
  {
    "id":
      "CCA71B63D5B0733302E571B69F49BB32",
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
&#x25B6; <b>Fourth</b> element in the request JSON file should be the list of <b><i>pools</i></b> within the <b><i>elements</i></b> property of the request JSON (the <b><i>diagram</i></b> property has been finished already at tis point). The list of <b><i>pools</i></b> should contain all <b><i>pools</i></b> that are used to hold <b><i>lanes</i></b> or <b><i>shapes</i></b>.<br/><br/>
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
&#x25B6; <b>Fifth</b> element in the request JSON file should be the list of shape <b><i>items</i></b>, referenced by <b><i>shapes</i></b>.<br/><br/>
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
&#x25B6; <b>Sixth</b> element in the request JSON file should be the list of connection <b><i>items</i></b>, referenced by <b><i>edges</i></b>.<br/><br/>
Both, the request JSON connection <b><i>items</i></b> and the BPMN <b><i>process</i></b> child nodes, provide an identifier <code>"id:"</code> (for request JSON) or <code>id</code> (for BPMN).<br/><br/><br/><br/>
</td>
</tr>
</table>

### Shapes
Do be done.

### Edges
Do be done.

### Pool items
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

### Shape items
Do be done.

### Edge items
Do be done.

### Lane items
In the case that the **diagram** is to be laid out and rendered with **lanes**, the **lanes** are *automatically* recognized by the fact, that they are *related* to structure building  **items** via the configured *laneRelevant* relation (see <code>"laneRelevant": "responsible"</code> within **<code>cfg</code> property**). The  **lanes** must not be of any of any specific **item** type (see <code>"type": "..."</code>), but they must be of **item** kind "OBJ" (see <code>"kind": "OBJ"</code>) and must not be of any of the structure building  **item** types (like <code>"type": "func"</code>, <code>"type": "evStart"</code>, <code>"type": "evIntermediate"</code>, <code>"type": "evEnd"</code>, <code>"type": "ruleXor"</code>, <code>"type": "ruleOr"</code>, <code>"type": "ruleAnd"</code> or <code>"type": "condition"</code>).

In the case that multiple **lanes** should be contained in a **pool** and the **lanes** should be in a defined order, it is recommended to define the **lanes** as a list of children (see <code>"children"</code>) within the **pool**. The **ids**, specified in the list of children, must refer to existing **lane** (**items**), that are typically *roles*, *groups*, *application systems* or *application services*.
