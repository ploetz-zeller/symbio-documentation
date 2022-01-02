# Graphic

# Introduction

The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics. The service expects the request as a JSON file and delivers the graphic as an HTML or SVG file.

# Task types

| JSON request type  | display | BPMN equivalent | Symbio legacy type |
|--------------------|---------|-----------------|--------------------|
| **definition and shape:**<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code> | **image:**![BPMN-serviceTask](media/GRAPHIC-task.png) | **definition:**<br /></code>&lt;task&gt;...&lt;/task&gt;</code><br />**image:**<br />![BPMN-task](media/BPMN-task.png) | **definition:**<br /><code>OT_FUNC</code><br />**shape:**<br /><code>ST_FUNC</code> |
|    | **image:**<br />![BPMN-serviceTask](media/GRAPHIC-serviceTask.png) | **definition:**<br /></code>&lt;serviceTask&gt;...&lt;/serviceTask&gt;</code><br />**image:**<br />![BPMN-serviceTask](media/BPMN-serviceTask.png) | g |
|      | f | f | g |
