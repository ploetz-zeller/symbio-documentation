# Graphic

* The *Symbio-Graphic-Service* combines a layouter and a renderer for the generation of BPMN and process flow graphics.
* The *Symbio-Graphic-Service* is intended to be callable from *Symbio.Manager* as well as from any other application, that supports HTTP requests.
* In order to support a wide range of requestors, the *Symbio-Graphic-Service* is designed to be as open as possible.
* The *Symbio-Graphic-Service* expects the data to layout (and render) as a JSON (a.k.a. **Request JSON**, prowided through the HTTP request body) and the functionality of the *Symbio-Graphic-Service* can be controlled by the ```configurations``` section at the top of the **Request JSON** (see chapter "The **Request JSON**" below).

## Table of contents
* [Endpoints](#endpoints)
  * [Check the HTTP connection](#checkconnection)
  * [Calculate a layout](#calculatelayout)
* [The **Request JSON**](#requestJSON)
* [The result](#result)
  * [The resulting connection path](#resultConnection)
  * [The result graph](#resultGraph)
* [BPMN sub-process and call activity](#bpmnCallActivity)
* [BPMN tasks](#bpnmTasks)
* [BPMN events](#bpnmEvents)
* [BPMN gateways](#bpnmGateways)
* [BPMN pools and lanes](#bpnmPoolsAndLanes)

## <a name="endpoints">Endpoints</a>
Currently the *Symbio-Graphic-Service* provides two endpoints:

1. **GET** or **POST** on **CheckConnection** with one parameter **name** or with a simple request JSON.
2. **POST** on **CalculateLayout** with a request JSON (see chapter **The request JSON** below).

### <a name="checkconnection">Check the HTTP connection</a>
* Sample request 1: **GET** or **POST** on <code>&lt;base-url&gt;:&lt;port&gt;/api/CheckConnection?name=Steffen</code>
* Sample request 2: **GET** or **POST** on <code>&lt;base-url&gt;:&lt;port&gt;/api/CheckConnection</code> with a body, containing a simple JSON like <code>{"name": "Steffen"}</code>
* Sample result on success: *Status:* 200 (OK); *Body:* <code>{\"date\":\" 09.01.2022 08:14:51\", \"greetings\":\"Hello, Steffen!\", \"system\":\"Microsoft Windows 10.0.19043\", \"platform\":\"Win32NT\", \"folder\":\"C:\\\\WINDOWS\", \"width\":\"64 bit\"}</code>
* Sample result on missing/wrong parameter **name** or body JSON: *Status:* 400 (Bad Request); *Body:* <code>09.01.2022 08:20:38: Please pass a name on the query string or in the request body!</code>
* Sample result on wrong <code>&lt;base-url&gt;</code> or <code>&lt;port&gt;</code>: *Status:* <code>ECONNREFUSED</code>

### <a name="calculatelayout">Calculate a layout</a>
* **POST** on <code>&lt;base-url&gt;:&lt;port&gt;/api/CalculateLayout</code> with a body, containing a request JSON (see chapter **The request JSON** below).
* Sample result on success: *Status:* 200 (OK); *Body:* ```calculation``` type 'cxn' and ```result``` type 'esvg' (embedded enriched SVG)
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

## <a name="requestJSON">The **Request JSON**</a>

* The request to calculate a layout (and render a graphic) is provided as a JSON (within the request body).
* The currently suported ```calculation``` types are ```cxn``` (route for a single connection path from a source node to a target node) and ```flow``` (directed graph with any number of nodes and edges).
* The currently suported ```result``` types are ```json``` (JSON, the recommended result type), ```ejson``` (JSON, enhanced with additional information), ```esvg``` (embedded SVG, enhanced with additional information), ```svg``` (embedded SVG, without additional information), ```sesvg``` (stand-alone SVG, enhanced with additional information) and ```ssvg``` (stand-alone SVG, without additional information).

For details (internal structure of the **Request JSON**) see [Request JSON](request_json.md).

## <a name="result">The result</a>

According to the requested ```calculation``` type (```cxn``` or ```flow```) the result can be
* the route for a single connection path or
* the layout (and rendering) of a directed graph

### <a name="resultConnection">The resulting connection path</a>
The connection path represents a single route from a source node to a target node. This route hast at least a start point (2D coordinates) and an end point (2D coordinates) and can have up to four additional interpolation points (each with 2D coordinates). The sections of the path are always orthogonal (either exact vertical or exact horizontal).

### <a name="resultGraph">The result graph</a>
The layed out (and rendered) graphic (directed graph), that is returned as a result of the service request, may contain several nodes (similar/comparable to BPMN elements), that can be of type:

- **Activity**: It is used to define an atomic or non-atomic piece of *work* within a *business process*. The graphical representation of an **Activity** can be bealized by:
  - **Sub-Process** and **Call Activity** as non-atomic pieces of *work* within a *business process*.
  - **Task** as atomic piece of *work* within a *business process*.
- **Event**: It represents something that *happens* during the course of a *business process*. It affects the flow of the *business process* and usually has a *cause* or an *impact* and in general requires or allows for a reaction.
- **Gateway**: It provides the graphical representation of execution semantics, used to control how pieces of *work* within a *business process* interact as they converge and diverge within a *business process*.
- **Pool**: It provides the graphical representation of *participants* (either a *partner entity* like a company, or a *partner role* like a buyer, a seller, or a manufacturer) in a *collaboration*. A **Pool** *may* or *may not* reference a *business process* - it can also serve as a *black box*.
- **Lane**: It is a sub-partition within a *business process* (often within a **Pool**) and will extend the entire length of the *business process*. A **Lane** is used to organize and categorize **Activities** within a Pool. The meaning of the **Lane** is up to the modeler.

## <a name="bpmnCallActivity">BPMN sub-process and call activity</a>

BPMN sub-processes can accure with different types.

For details (about BPMN events and how they are used by the *Symbio-Graphic-Service*) see document [BPMN sub-processes and call activities](elements_subprocesses.md).

## <a name="bpnmTasks">BPMN tasks</a>

BPMN tasks can accure with different types and with different markers.

For details (about BPMN tasks and how they are used by the *Symbio-Graphic-Service*) see document [BPMN tasks](elements_tasks.md).

## <a name="bpnmEvents">BPMN events</a>

BPMN events can occur at different locations, with different continuations and with different types.

For details (about BPMN sub processes and how they are used by the *Symbio-Graphic-Service*) see document [BPMN events](elements_events.md).

## <a name="bpnmGateways">BPMN gateways</a>

BPMN gateways can occur with different types.

For details (about BPMN gateways and how they are used by the *Symbio-Graphic-Service*) see document [BPMN events](elements_gateways.md).

## <a name="bpnmPoolsAndLanes">BPMN pools and lanes</a>

BPMN pools and lanes can represent different contexts.

For details (about BPMN pools and lanes and how they are used by the *Symbio-Graphic-Service*) see document [BPMN events](elements_pools_and_lanes.md).
