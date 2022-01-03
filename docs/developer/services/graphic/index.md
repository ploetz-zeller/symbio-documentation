# Graphic

# Introduction

The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics. The service expects the request as a JSON file and delivers the graphic as an HTML or SVG file.

## The request JSON

The request to calculate a layout and render a graphic is provided as a JSON file.

For details see [Request JSON](request_json.md).

## The result graphic

The rendered graphic, that is returned as a result of the service request, may contain several BPMN elements, that can be of:
- **Activities** are used to define an atomic or non-atomic piece of *work* within a *business process*. The graphical representation of **Activities** can be bealized by:
  - **Sub-Processes** and **Call Activities** are non-atomic pieces of *work* within a *business process*.
  - **Tasks** are atomic pieces of *work* within a *business process*.
- **Events** represent something that *happens* during the course of a *business process*. They affect the flow of the *business process* and usually have a *cause* or an *impact* and in general require or allow for a reaction.
- **Gateways** provide the graphical representation of execution semantics, used to control how pieces of *work* within a *business process* interact as they converge and diverge within a *business process*.
- **Pools** provide the graphical representation of *participants* (either a *partner entity* like a company, or a *partner role* like a buyer, a seller, or a manufacturer) in a *collaboration*. A **Pool** *may* or *may not* reference a *business process* - it can also serve as a *black box*.
- **Lanes** are sub-partitions within a *business process* (often within a **Pool**) and will extend the entire length of the *business process*. **Lanes** are used to organize and categorize **Activities** within a Pool. The meaning of the **Lanes** is up to the modeler.

## BPMN sub-processes and call activities

BPMN sub-processes can accure with different types.

For details see [Sub-processes](elements_subprocesses.md).

## BPMN tasks

BPMN tasks can accure with different types and with different markers.

For details see [Tasks](elements_tasks.md).

## BPMN events

BPMN events can occur at different locations, with different continuations and with different types.

For details see [Events](elements_events.md).

## BPMN gateways

## BPMN pools and lanes
