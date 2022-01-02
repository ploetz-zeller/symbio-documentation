# Events

# Introduction
Events can occur at different locations, with different continuations and with different types.

### Event continuations, that are defined by BPMN are:
- interrupting
- non-interrupting

Any event continuation can be combined with any event location, except <code>non-interrupting</code> and <code>end</code>.

### Event locations, that are defined by BPMN are:
- start
- intermediate
- end

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/ shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStartNonInterrupting",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>} | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart"</code><br /><code>}</code><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStartNonInterrupting"</code><br /><code>}</code> | *interrupting:*<br />![GRAPHIC-eventStart](media/GRAPHIC-eventStart.png)<br />*non-interrupting:*<br />![GRAPHIC-eventStartNonInterrupting](media/GRAPHIC-eventStartNonInterrupting.png) | *interrupting:*<br /></code>&lt;startEvent&gt;...&lt;/startEvent&gt;</code><br /><br />*non-interrupting:*<br />&lt;startEvent isInterrupting="false"&gt; ... &lt;/startEvent&gt; | *interrupting:*<br />![GRAPHIC-eventStart](media/BPMN-eventStart.png)<br />*non-interrupting:*<br />![BPMN-eventStartNonInterrupting](media/BPMN-eventStartNonInterrupting.png) |  |
| 2 | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br />*non-interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate</code>-<br /><code>NonInterrupting",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code> | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate"</code><br /><code>}</code><br /><br />*non-interrupting:*<br />"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate</code>-<br /><code>NonInterrupting"</code><br /><code>}</code> | *interrupting:*<br />![GRAPHIC-eventIntermediate](media/GRAPHIC-eventIntermediate.png)<br />*non-interrupting:*<br />![GRAPHIC-eventIntermediateNonInterrupting](media/GRAPHIC-eventIntermediateNonInterrupting.png) | *interrupting:*<br /></code>&lt;intermediateThrowEvent&gt; ... &lt;/intermediateThrowEvent&gt;</code><br /><br />*non-interrupting:*<br /></code>&lt;intermediateThrowEvent isInterrupting="false"&gt; ... &lt;/intermediateThrowEvent&gt;</code> | *interrupting:*<br />![BPMN-eventIntermediate](media/BPMN-eventIntermediate.png)<br />*non-interrupting:*<br />![BPMN-eventIntermediateNonInterrupting](media/BPMN-eventIntermediateNonInterrupting.png) |  |
| 3 | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evEnd",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code> | *interrupting:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evEnd",</code><br /><code>}</code><br /> | *interrupting:*<br />![GRAPHIC-eventEnd](media/GRAPHIC-eventEnd.png) | *interrupting:*<br /></code>&lt;endEvent&gt; ... &lt;/endEvent&gt;</code><br /> | *interrupting:*<br />![BPMN-eventEnd](media/BPMN-eventEnd.png) |  |

### Event types, that are defined by BPMN are:
- none
- throw message
- catch message
- timer
- throw error
- catch error
- throw escalation
- catch escalation
- throw cancel
- catch cancel
- throw compensation
- catch compensation
- conditional
- throw link
- catch link
- throw signal
- catch signal
- terminate
- throw multiple
- catchm ultiple
- parallel multiple
