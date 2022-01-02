# Graphic

# Introduction

The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics. The service expects the request as a JSON file and delivers the graphic as an HTML or SVG file.

# Task types and task markers

The task types, that are defined by BPMN are:
- task
- service
- send
- receive
- receive and instantiate process
- manual
- user
- business role
- script

| No. | JSON request  | display | BPMN equivalent | Symbio legacy |
|-----|---------------|---------|-----------------|---------------|
| 1 | ***definition:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br />***shape:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ***image:***<br />![BPMN-serviceTask](media/GRAPHIC-task.png) | ***definition:***<br /></code>&lt;task&gt;...&lt;/task&gt;</code><br />***image:***<br />![BPMN-task](media/BPMN-task.png) | ***definition:***<br /><code>OT_FUNC</code><br />***shape:***<br /><code>ST_FUNC</code> |
| 2 | ***definition:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "funcTypeService"</code><br /><code>}</code><br />***shape:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ***image:***<br />![BPMN-serviceTask](media/GRAPHIC-serviceTask.png) | ***definition:***<br /></code>&lt;serviceTask&gt;...&lt;/serviceTask&gt;</code><br />***image:***<br />![BPMN-serviceTask](media/BPMN-serviceTask.png) | ditto |
| 3 | ***definition:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "funcTypeSend"</code><br /><code>}</code><br />***shape:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ***image:***<br />![BPMN-serviceTask](media/GRAPHIC-dendTask.png) | ***definition:***<br /></code>&lt;serviceTask&gt;...&lt;/serviceTask&gt;</code><br />***image:***<br />![BPMN-serviceTask](media/BPMN-sendTask.png) | ditto |
| 4 | ***definition:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "funcTypeReceive"</code><br /><code>}</code><br />***shape:***<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>}</code><br /> | ***image:***<br />![BPMN-serviceTask](media/GRAPHIC-receiveTask.png) | ***definition:***<br /></code>&lt;serviceTask&gt;...&lt;/serviceTask&gt;</code><br />***image:***<br />![BPMN-serviceTask](media/BPMN-receiveTask.png) | ditto |
