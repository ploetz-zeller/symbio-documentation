# Events

# Introduction
Events can occur at different locations, with different continuations and with different types.

### Event locations, that are defined by BPMN are:
- start
- intermediate
- end

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/ shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart",</code><br /><code>}</code><br /> | ![GRAPHIC-eventStart](media/GRAPHIC-eventStart.png) | </code>&lt;startEvent&gt;...&lt;/startEvent&gt;</code><br /> | ![BPMN-eventStart](media/BPMN-eventStart.png) |  |
| 2 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evIntermediate",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evStart",</code><br /><code>}</code><br /> | ![GRAPHIC-eventIntermediate](media/GRAPHIC-eventIntermediate.png) | </code>&lt;intermediateThrowEvent&gt;...&lt;/intermediateThrowEvent&gt;</code><br /> | ![BPMN-eventIntermediate](media/BPMN-eventIntermediate.png) |  |
| 3 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evEnd",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "evEnd",</code><br /><code>}</code><br /> | ![GRAPHIC-eventEnd](media/GRAPHIC-eventEnd.png) | </code>&lt;endEvent&gt;...&lt;/endEvent&gt;</code><br /> | ![BPMN-eventEnd](media/BPMN-eventEnd.png) |  |

### Event continuations, that are defined by BPMN are:
- interrupting
- non-interrupting

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
