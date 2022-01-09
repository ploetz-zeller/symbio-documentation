# BPMN tasks

## Introduction

Tasks are atomic pieces of *work* within a *business process*. They are - besides the *sub-processes* and *call activities* - a graphical representation of **Activities**.

Tasks can accure with different types and with different markers.

All task types can be combined with all task markers.

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

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/&nbsp;shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-task](media/GRAPHIC-task.png) | </code>&lt;task&gt;...&lt;/task&gt;</code><br /> | ![BPMN-task](media/BPMN-task.png) |
| 2 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "service"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![BPMN-serviceTask](media/GRAPHIC-serviceTask.png) | </code>&lt;serviceTask&gt; ... &lt;/serviceTask&gt;</code><br /> | <br />![GRAPHIC-serviceTask](media/BPMN-serviceTask.png) |
| 3 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "send"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![BPMN-sendTask](media/GRAPHIC-sendTask.png) | <br /></code>&lt;sendTask&gt; ... &lt;/sendTask&gt;</code><br /> | ![GRAPHIC-sendTask](media/BPMN-sendTask.png) |
| 4 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "receive"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![BPMN-receiveTask](media/GRAPHIC-receiveTask.png) | <br /></code>&lt;receiveTask&gt; ... &lt;/receiveTask&gt;</code><br /> | <br />![GRAPHIC-receiveTask](media/BPMN-receiveTask.png) |
| 5 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "user"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![BPMN-userTask](media/GRAPHIC-userTask.png) | <br /></code>&lt;userTask&gt; ... &lt;/userTask&gt;</code><br /> | <br />![GRAPHIC-userTask](media/BPMN-userTask.png) |
| 6 | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcType": "manual"</code><br /><code>}</code><br /> | <br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![BPMN-manualTask](media/GRAPHIC-manualTask.png) | <br /></code>&lt;manualTask&gt; ... &lt;/manualTask&gt;</code><br /> | <br />![GRAPHIC-manualTask](media/BPMN-manualTask.png) |

### The task markers, that are defined by BPMN are:
- none
- loop
- parallel multiple
- sequential multiple
- compensation
- compensation loop

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/&nbsp;shape | Graphic display | BPMN definition | BPMN&nbsp;sdisplay |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| A | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-task](media/GRAPHIC-task.png) | </code>&lt;task&gt; ... &lt;/task&gt;</code><br /> | ![BPMN-task](media/BPMN-task.png) |
| B | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcMarker": "loop"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-taskWithLoop](media/GRAPHIC-taskWithLoop.png) | </code>&lt;task&gt; ...<br />&lt;standard- <br />LoopCharacteristics /&gt;<br /> ... &lt;/task</code><br /> | ![BPMN-taskWithLoop](media/BPMN-taskWithLoop.png) |
| C | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcMarker": "parallelMultiple"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-taskWithParallelMultiple](media/GRAPHIC-taskWithParallelMultiple.png) | </code>&lt;task&gt; ...<br />&lt;multiInstance-<br />LoopCharacteristics /&gt;<br /> ... &lt;/task&gt;</code><br /> | ![BPMN-taskWithParallelMultiple](media/BPMN-taskWithParallelMultiple.png) |
| D | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcMarker": "sequentialMultiple"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-taskWithSequentialMultiple](media/GRAPHIC-taskWithSequentialMultiple.png) | </code>&lt;task&gt; ...<br />&lt;multiInstance-<br />LoopCharacteristics isSequential="true" /&gt;<br /> ... &lt;/task&gt;</code><br /> | ![BPMN-taskWithSequentialMultiple](media/BPMN-taskWithSequentialMultiple.png) |
| E | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcMarker": "compensation"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-taskWithCompensation](media/GRAPHIC-taskWithCompensation.png) | </code>&lt;task isFor-<br />Compensation="true"&gt;<br /> ... &lt;/task&gt;</code><br /> | ![BPMN-taskWithCompensation](media/BPMN-taskWithCompensation.png) |
| F | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"funcMarker": "compensationLoop"</code><br /><code>}</code><br /> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func"</code><br /><code>}</code><br /> | ![GRAPHIC-taskWithLoopAndCompensation](media/GRAPHIC-taskWithLoopAndCompensation.png) | </code>&lt;task isFor-<br />Compensation="true"&gt; ...<br />&lt;standard- <br />LoopCharacteristics /&gt;<br /> ...&lt;/task&gt;</code><br /> | ![BPMN-taskWithLoopAndCompensation](media/BPMN-taskWithLoopAndCompensation.png) |
