# Graphic

# Introduction

The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics. The service expects the request as a JSON file and delivers the graphic as an HTML or SVG file.

## Events

Events can occur at different locations, with different continuations and with different types.

### Event locations, that are defined by BPMN are:
- start
- intermediate
- end

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

## Task

Tasks can accure with different types and with different markers.


