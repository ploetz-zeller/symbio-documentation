# Graphic

## Introduction

The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics.

## Endpoints
Currently the *Symbio-Graphic-Service* provides two endpoints:

1. **GET** or **POST** on **CheckConnection** with one parameter **name** or with a simple request JSON.
2. **POST** on **CalculateLayout** with a request JSON (see chapter **The request JSON** below).

### CheckConnection
* Sample request 1: **GET** or **POST** on <code>&lt;base-url&gt;:&lt;port&gt;/api/CheckConnection?name=Steffen</code>
* Sample request 2: **GET** or **POST** on <code>&lt;base-url&gt;:&lt;port&gt;/api/CheckConnection</code> with a body, containing a simple JSON like <code>{"name": "Steffen"}</code>
* Sample result on success: *Status:* 200 (OK); *Body:* <code>{\"date\":\" 09.01.2022 08:14:51\", \"greetings\":\"Hello, Steffen!\", \"system\":\"Microsoft Windows 10.0.19043\", \"platform\":\"Win32NT\", \"folder\":\"C:\\\\WINDOWS\", \"width\":\"64 bit\"}</code>
* Sample result on missing/wrong parameter **name** or body JSON: *Status:* 400 (Bad Request); *Body:* <code>09.01.2022 08:20:38: Please pass a name on the query string or in the request body!</code>
* Sample result on wrong <code>&lt;base-url&gt;</code> or <code>&lt;port&gt;</code>: *Status:* <code>ECONNREFUSED</code>

### CalculateLayout
* **POST** on <code>&lt;base-url&gt;:&lt;port&gt;/api/CalculateLayout</code> with a body, containing a request JSON (see chapter **The request JSON** below).
* Sample result on success: *Status:* 200 (OK); *Body:* calculation type 'cxn' and calculation type 'esvg' (embedded enriched SVG)
  ```html
  <!-- Bounding: Width="410" Height="410" -->
  <!-- Created: By="Symbio.Service.Graphic.Managed" On="09.01.2022 05:13:49" -->
  <!-- Version: Release="4,99" Revision="1" -->
  <!-- Performance: Prepare="00s:000ms" Parse="00s:000ms" Calculate="00s:000ms" -->
  <rect fill="#f0fff0" id="source" stroke="none" stroke-width="1pt" x="100" y="100" width="100" height="100"></rect>
  <rect fill="#fff0f0" id="target" stroke="none" stroke-width="1pt" x="300" y="300" width="100" height="100"></rect>
  <g class="connection">
    <defs>
      <marker id="MARKER_not-provided" viewBox="0 0 5 10" refX="5" refY="5" markerUnits="userSpaceOnUse" markerWidth="10" markerHeight="10" orient="270">
        <path d="M 0,0 l 5,5 l -5,5 z" style="fill:#878787; stroke:none; stroke-width:0.0pt;"></path>
      </marker>
    </defs>
    <polyline data-pz-shape-id="not-provided" class="selectable" points="150,100 150,90 410,90 410,410 350,410 350,400" style="stroke:#878787; stroke-opacity:1.0; stroke-dasharray:null; fill:none; fill-opacity:1.0;  stroke-linecap:null; stroke-linejoin:null; stroke-width:1pt;" marker-start="" marker-end="url(#MARKER_not-provided)" ></polyline>
  </g>
  ```
* Sample result on wrong body JSON property **calculation**: *Status:* 400 (Bad Request); *Body:* <code>Currently the calculation type '' is not supported!</code>
* Sample result on wrong body JSON property **result**: *Status:* 400 (Bad Request); *Body:* <code>Currently the result type '' is not supported for calculation type 'cxn'!</code>
* Sample result on wrong <code>&lt;base-url&gt;</code> or <code>&lt;port&gt;</code>: *Status:* <code>ECONNREFUSED</code>

The service expects the request as a JSON file and delivers the graphic as an HTML or SVG file.

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

For details see [BPMN sub-processes and call activities](elements_subprocesses.md).

## BPMN tasks

BPMN tasks can accure with different types and with different markers.

For details see [BPMN tasks](elements_tasks.md).

## BPMN events

BPMN events can occur at different locations, with different continuations and with different types.

For details see [BPMN events](elements_events.md).

## BPMN gateways

*To be done.*

## BPMN pools and lanes

*To be done.*
