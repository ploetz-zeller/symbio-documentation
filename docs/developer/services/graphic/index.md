# Graphic

# Introduction

The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics. The service expects the request as a JSON file and delivers the graphic as an HTML or SVG file.

# Task types

| JSON request type  | display | BPMN equivalent | Symbio legacy type |
|--------------------|---------|-----------------|--------------------|
| definition and shape:<br /><code>"properties": {</code><br /><code>&nbsp;&nbsp;"type": "func",</code><br /><code>&nbsp;&nbsp;"kind": "OBJ"</code><br /><code>}</code> | f | definition:<br /></code>&lt;task&gt;...&lt;/task&gt;</code> | <code>OT_FUNC</code><br /><code>ST_FUNC</code> |
|    | f | f | g |
|      | f | f | g |
|--------------------|---------|-----------------|--------------------|
