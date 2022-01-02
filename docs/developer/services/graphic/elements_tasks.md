# Task

## Introduction

Tasks can accure with different types and with different markers.

### The task types, that are defined by BPMN are:
- none
- service
- send
- receive
- receive and instantiate process
- manual
- user
- business role
- script

#### The Symbio legacy definition for tasks is:
*definition:* <code>OT_FUNC</code>
*shape:* <code>ST_FUNC</code>

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/ shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-serviceTask](media/GRAPHIC-task.png) | </code>&lt;task&gt;...&lt;/task&gt;</code><br /> | ![BPMN-task](media/BPMN-task.png) |  |
| 2 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "service"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-serviceTask](media/GRAPHIC-serviceTask.png) | </code>&lt;serviceTask&gt; ... &lt;/serviceTask&gt;</code><br /> | <br />![GRAPHIC-serviceTask](media/BPMN-serviceTask.png) | ditto |
| 3 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "send"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-sendTask](media/GRAPHIC-sendTask.png) | <br /></code>&lt;sendTask&gt; ... &lt;/sendTask&gt;</code><br /> | ![GRAPHIC-sendTask](media/BPMN-sendTask.png) | ditto |
| 4 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "receive"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-receiveTask](media/GRAPHIC-receiveTask.png) | <br /></code>&lt;receiveTask&gt; ... &lt;/receiveTask&gt;</code><br /> | <br />![GRAPHIC-receiveTask](media/BPMN-receiveTask.png) | ditto |
| 5 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "user"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-userTask](media/GRAPHIC-userTask.png) | <br /></code>&lt;userTask&gt; ... &lt;/userTask&gt;</code><br /> | <br />![GRAPHIC-userTask](media/BPMN-userTask.png) | ditto |
| 6 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "manual"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-manualTask](media/GRAPHIC-manualTask.png) | <br /></code>&lt;manualTask&gt; ... &lt;/manualTask&gt;</code><br /> | <br />![GRAPHIC-manualTask](media/BPMN-manualTask.png) | ditto |

### The task markers, that are defined by BPMN are:
- none
- loop
- parallel multiple
- sequential multiple
- compensation
- compensation loop

