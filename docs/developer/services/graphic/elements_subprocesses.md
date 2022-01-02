# Sub-processes

Sub-processes can accure with different types.

### The sub-provess types, that are defined by BPMN are:
- none
- loop
- muilti-instance
- compensation
- ad hoc

| No. | JSON&nbsp;request&nbsp;/&nbsp;definition | JSON&nbsp;request&nbsp;/&nbsp;shape | Graphic display | BPMN definition | BPMN display |
|-----|---------------------------|----------------------|-----------------|-----------------|--------------|
| 1 | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code><br /><br />*or:*<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ",</code><br /><code>&nbsp;&nbsp;"processMarker": "none"</code><br /><code>}</code> | <code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "subProcess"</code><br /><code>}</code><br /> | ![GRAPHIC-subProcess](media/GRAPHIC-subProcess.png) | </code>&lt;subProcess&gt;...&lt;/subProcess&gt;</code><br /> | ![BPMN-subProcess](media/BPMN-subProcess.png) |
