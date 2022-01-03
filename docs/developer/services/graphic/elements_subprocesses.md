# BPMN sub-processes and call activities

Sub-processes and call activities are non-atomic pieces of *work* within a *business process*. They are - besides the *tasks* - a graphical representation of **Activities**.

Sub-processes can occure with different types.

### The sub-provess types, that are defined by BPMN are:
- none
- loop
- muilti-instance
- compensation
- ad hoc
- transaction

A *sub-process* is a non-atomic (compound) **Activity** that is included within a *business process* or a choreography. It is compound in that it can be broken down into a finer level of detail through a set of sub-**Activities**.

A *transaction* is a *sub-process* that is supported by a special protocol that insures that all parties involved have complete agreement that the activity should be completed or cancelled. The attributes of the activity will determine if the activity is a transaction.

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/&nbsp;shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /><br />*or:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "none"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcess](media/GRAPHIC-subProcess.png) | </code>&lt;subProcess&gt; ... <br />&lt;/subProcess&gt;</code><br /> | ![BPMN-subProcess](media/BPMN-subProcess.png) |
| 2 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "parallelMultiple"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithParallelMultiple](media/GRAPHIC-subProcessWithParallelMultiple.png) | </code>&lt;subProcess&gt; ... <br />&lt;multiInstance- <br />LoopCharacteristics/&gt; ... &lt;/subProcess&gt;</code><br /> | ![BPMN-subProcessWithParallelMultiple](media/BPMN-subProcessWithParallelMultiple.png) |
| 3 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "loop"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithLoop](media/GRAPHIC-subProcessWithLoop.png) | </code>&lt;subProcess&gt; ... <br />&lt;standardLoop-<br />Characteristics/&gt; ... &lt;/subProcess&gt;</code><br /> | ![BPMN-subProcessWithLoop](media/BPMN-subProcessWithLoop.png) |
| 4 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "compensation"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithCompensation](media/GRAPHIC-subProcessWithCompensation.png) | </code>&lt;subProcess isFor-<br />Compensation="true"&gt; ... <br />&lt;standardLoop-<br />Characteristics/&gt; ... &lt;/subProcess&gt;</code><br /> | ![BPMN-subProcessWithCompensation](media/BPMN-subProcessWithCompensation.png) |
| 5 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "adHoc"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithAdHoc](media/GRAPHIC-subProcessWithAdHoc.png) | </code>&lt;adHocSubProcess&gt; ... &lt;/adHocSubProcess&gt;</code><br /> | ![BPMN-subProcessWithAdHoc](media/BPMN-subProcessWithAdHoc.png) |
| 6 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "transaction",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /><br />*or:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "transaction",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "none"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "transaction"</code><br /><code>}</code><br /> | ![GRAPHIC-transaction](media/GRAPHIC-transaction.png) | </code>&lt;transaction&gt; ... <br />&lt;/transaction&gt;</code><br /> | ![BPMN-transaction](media/BPMN-transaction.png) |

### BPMN call activity

A *call activity* identifies a point in the *business process* where a global *sub-process* or a global *task* is used. The *call activity* acts as a wrapper for the invocation of a global *sub-process* or a global *task* within the *business process*. 

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/&nbsp;shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 7 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "callActivity",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /><br />*or:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "callActivity",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "none"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "callActivity"</code><br /><code>}</code><br /> | ![GRAPHIC-callActivity](media/GRAPHIC-callActivity.png) | </code>&lt;callActivity&gt; ... <br />&lt;/callActivity&gt;</code><br /> | ![BPMN-callActivity](media/BPMN-callActivity.png) |
