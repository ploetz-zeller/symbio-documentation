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

| No. | JSON request / definition | JSON request / shape | display | BPMN equivalent |
|-----|---------------------------|----------------------|---------|-----------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-serviceTask](media/GRAPHIC-task.png) | ***definition:***<br /></code>&lt;task&gt;...&lt;/task&gt;</code><br />***image:***<br />![BPMN-task](media/BPMN-task.png) |  |
| 2 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "funcTypeService"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-serviceTask](media/GRAPHIC-serviceTask.png) | ***definition:***<br /></code>&lt;serviceTask&gt;...&lt;/serviceTask&gt;</code><br />***image:***<br />![BPMN-serviceTask](media/BPMN-serviceTask.png) | ditto |
| 3 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "funcTypeSend"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-sendTask](media/GRAPHIC-sendTask.png) | ***definition:***<br /></code>&lt;sendTask&gt;...&lt;/sendTask&gt;</code><br />***image:***<br />![BPMN-sendTask](media/BPMN-sendTask.png) | ditto |
| 4 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "funcTypeReceive"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ![BPMN-receiveTask](media/GRAPHIC-receiveTask.png) | ***definition:***<br /></code>&lt;receiveTask&gt;...&lt;/receiveTask&gt;</code><br />***image:***<br />![BPMN-receiveTask](media/BPMN-receiveTask.png) | ditto |

### The task markers, that are defined by BPMN are:
- none
- loop
- parallel multiple
- sequential multiple
- compensation
- compensation loop

