# Events

# Introduction
Events can occur with different continuations, at different locations and with different types.

### Event continuations, that are defined by BPMN are:
- interrupting
- non-interrupting

Any event continuation can be combined with any event location, except <code>non-interrupting</code> and <code>end</code>.

### Event locations, that are defined by BPMN are:
- start
- intermediate
- end

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/ shape | Graphic display | BPMN definition | BPMN display |
|-----|------------------------------------------|--------------------------------|-----------------|-----------------|--------------|
| 1 | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStartNonInterrupting",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>} </code> | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart"</code><br /><code>}</code><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStartNonInterrupting"</code><br /><code>}</code> | *interrupting:*<br />![GRAPHIC-eventStart](media/GRAPHIC-eventStart.png)<br />*non-interrupting:*<br />![GRAPHIC-eventStartNonInterrupting](media/GRAPHIC-eventStartNonInterrupting.png) | *interrupting:*<br />&lt;startEvent&gt;...&lt;/startEvent&gt;<br /><br />*non-interrupting:*<br />&lt;startEvent isInterrupting="false"&gt; ... &lt;/startEvent&gt; | *interrupting:*<br />![GRAPHIC-eventStart](media/BPMN-eventStart.png)<br />*non-interrupting:*<br />![BPMN-eventStartNonInterrupting](media/BPMN-eventStartNonInterrupting.png) |
| 2 | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate</code>-<br /><code>NonInterrupting",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code> | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate"</code><br /><code>}</code><br /><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate</code>-<br /><code>NonInterrupting"</code><br /><code>}</code> | *interrupting:*<br />![GRAPHIC-eventIntermediate](media/GRAPHIC-eventIntermediate.png)<br />*non-interrupting:*<br />![GRAPHIC-eventIntermediateNonInterrupting](media/GRAPHIC-eventIntermediateNonInterrupting.png) | *interrupting:*<br />&lt;intermediateThrowEvent&gt; ... &lt;/intermediateThrowEvent&gt;<br /><br />*non-interrupting:*<br />&lt;intermediateThrowEvent isInterrupting="false"&gt; ... &lt;/intermediateThrowEvent&gt; | *interrupting:*<br />![BPMN-eventIntermediate](media/BPMN-eventIntermediate.png)<br />*non-interrupting:*<br />![BPMN-eventIntermediateNonInterrupting](media/BPMN-eventIntermediateNonInterrupting.png) |
| 3 | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evEnd",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code> | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evEnd",</code><br /><code>}</code><br /> | *interrupting:*<br />![GRAPHIC-eventEnd](media/GRAPHIC-eventEnd.png) | *interrupting:*<br />&lt;endEvent&gt; ... &lt;/endEvent&gt; | *interrupting:*<br />![BPMN-eventEnd](media/BPMN-eventEnd.png) |

### Event types, that are defined by BPMN are:
- none
- throw message;         add <code>"evType": "throwMessage"</code> to <code>"properties"</code> on JSON request definition
- catch message;         add <code>"evType": "catchMessage"</code> to <code>"properties"</code> on JSON request definition
- timer;                 add <code>"evType": "timer"</code> to <code>"properties"</code> on JSON request definition
- throw error;           add <code>"evType": "throwError"</code> to <code>"properties"</code> on JSON request definition
- catch error;           add <code>"evType": "catchError"</code> to <code>"properties"</code> on JSON request definition
- throw escalation;      add <code>"evType": "throwEscalation"</code> to <code>"properties"</code> on JSON request definition
- catch escalation;      add <code>"evType": "catchEscalation"</code> to <code>"properties"</code> on JSON request definition
- throw cancel;          add <code>"evType": "throwCancel"</code> to <code>"properties"</code> on JSON request definition
- catch cancel;          add <code>"evType": "catchCancel"</code> to <code>"properties"</code> on JSON request definition
- throw compensation;    add <code>"evType": "throwCompensation"</code> to <code>"properties"</code> on JSON request definition
- catch compensation;    add <code>"evType": "catchCompensation"</code> to <code>"properties"</code> on JSON request definition
- conditional;           add <code>"evType": "conditional"</code> to <code>"properties"</code> on JSON request definition
- throw link;            add <code>"evType": "throwLink"</code> to <code>"properties"</code> on JSON request definition
- catch link;            add <code>"evType": "catchLink"</code> to <code>"properties"</code> on JSON request definition
- throw signal;          add <code>"evType": "throwSignal"</code> to <code>"properties"</code> on JSON request definition
- catch signal;          add <code>"evType": "catchSignal"</code> to <code>"properties"</code> on JSON request definition
- terminate;             add <code>"evType": "terminate"</code> to <code>"properties"</code> on JSON request definition
- throw multiple;        add <code>"evType": "throwMultiple"</code> to <code>"properties"</code> on JSON request definition
- catchm ultiple;        add <code>"evType": "catchMultiple"</code> to <code>"properties"</code> on JSON request definition
- parallel multiple;     add <code>"evType": "parMultiple"</code> to <code>"properties"</code> on JSON request definition

### All available combinations of event continuations, locations and types:
![BPMN-eventCombinations](media/BPMN-eventCombinations.png)
