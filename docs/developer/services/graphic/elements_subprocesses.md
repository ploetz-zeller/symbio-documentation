# BPMN sub-processes and call activities

Sub-processes and call activities are non-atomic pieces of *work* within a *business process*. They are - besides the *tasks* - a graphical representation of **Activities**.

Sub-processes can occure with different types.

### The sub-provess types, that are defined by BPMN are:
- none
- loop
- muilti-instance
- compensation
- ad hoc

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/&nbsp;shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /><br />*or:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "none"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcess](media/GRAPHIC-subProcess.png) | </code>&lt;subProcess&gt;...&lt;/subProcess&gt;</code><br /> | ![BPMN-subProcess](media/BPMN-subProcess.png) |
| 2 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "parallelMultiple"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithParallelMultiple](media/GRAPHIC-subProcessWithParallelMultiple.png) | </code>&lt;subProcess&gt; ... &lt;multiInstance- <br />LoopCharacteristics/&gt; ... &lt;/subProcess&gt;</code><br /> | ![BPMN-subProcessWithParallelMultiple](media/BPMN-subProcessWithParallelMultiple.png) |
| 3 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "loop"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithLoop](media/GRAPHIC-subProcessWithLoop.png) | </code>&lt;subProcess&gt; ... &lt;standardLoop-<br />Characteristics/&gt; ... &lt;/subProcess&gt;</code><br /> | ![BPMN-subProcessWithLoop](media/BPMN-subProcessWithLoop.png) |
| 4 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "compensation"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithCompensation](media/GRAPHIC-subProcessWithCompensation.png) | </code>&lt;subProcess isFor-<br />Compensation="true"&gt; ... &lt;standardLoop-<br />Characteristics/&gt; ... &lt;/subProcess&gt;</code><br /> | ![BPMN-subProcessWithCompensation](media/BPMN-subProcessWithCompensation.png) |
| 5 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "adHoc"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcessWithAdHoc](media/GRAPHIC-subProcessWithAdHoc.png) | </code>&lt;adHocSubProcess&gt; ... &lt;/adHocSubProcess&gt;</code><br /> | ![BPMN-subProcessWithAdHoc](media/BPMN-subProcessWithAdHoc.png) |
