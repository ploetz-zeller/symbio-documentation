# Graphic

**api-version**: 2.0

Retrieves a specific graphic's .svg file.

```
GET /{collectionId}/{storageId}/_api/rest/diagram/{diagramId}/render/{cultureId}/{layoutKey}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |
| diagramId | path | true | string | The ID of the diagram. |
| cultureId | path | true | string | The ID of the diagram language / localization. |
| layoutKey | path | true | string | The layout key for the diagram. \\Possible values: detailed / vertical / horizontal / verticalSwimlane/ horizontalSwimlane / graphic / processMatrix / customerMatrix / entityRelationship |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| svg | image/svg+xml | The Scalable vector graphics format that represents the graphic of the diagram in the selected layout. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Example

### Get a diagram of the diagram with the ID provided

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/diagram/fa596aef-fa06-4f5c-9b55-e7c36a478c2a/render/1033/detailed
```

#### Reponse (200 OK)
```xml
<svg xmlns="http://www.w3.org/2000/svg" width="161" height="277" style="background-color: Transparent" version="1.1" shape-rendering="crispEdges" text-rendering="crispEdges">
    <script type="text/javascript">
        <![CDATA[
            if (PZ != null && PZ.Sy != null && PZ.Sy.BasePlugin != null && PZ.Sy.BasePlugin.Diagram != null) {
                PZ.Sy.BasePlugin.Diagram.DisplayedAttributeTypes = ['AT_NAME'];
                PZ.Sy.BasePlugin.Diagram.DisplayedItemTypes = ['OT_FUNC', 'OTX_EV_START', 'OTX_EV_END'];
            }
        ]]>
    </script>
    <g>
        <!-- STX_EV_START /W:500 /H:215 -->
        <rect x="14.5" y="14.5" rx="0" ry="0" width="141" height="61" style="stroke:NONE; stroke-width:0px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#A6A6A6; fill-opacity:1;" />
        <ellipse cx="144.5669" cy="44.64567" rx="7.086614" ry="7.086614" style="shape-rendering:auto; stroke:#FFFFFF; stroke-width:1px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#A6A6A6; fill-opacity:1;" />
        <rect x="18.5" y="18.5" rx="0" ry="0" width="114" height="53" style="stroke:NONE; stroke-width:0px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#FFFFFF; fill-opacity:1;" />
        <text class="" x="19.5" y="29.84669" text-anchor="start" style="fill:#444444;font-family:Segoe UI;font-weight:400;font-style:normal;font-size:8.775pt;text-decoration:none;">
            <tspan class="" x="19.5" dy="0">Start</tspan>
        </text>
    </g>
    <rect id="G1_53099ec8-b6f1-42f4-a5e3-b421788756be_1" title="" data-pz-guid="53099ec8-b6f1-42f4-a5e3-b421788756be" data-pz-type="OTX_EV_START" data-pz-shape-id="f95b8180-04e6-49c5-9488-6c5c45016370" data-pz-diagram-id="" class="" onclick="parent.Symbol_Click(this, '53099ec8-b6f1-42f4-a5e3-b421788756be');" onmouseover="parent.Symbol_MouseOver(this);" onmouseout="parent.Symbol_MouseOut(this);" x="14.5" y="14.5" width="142" height="61" style="z-index:10001; stroke:#000; stroke-opacity:0.0; fill:#000; fill-opacity:0.0; cursor:pointer;" />
    <g>
        <!-- ST_FUNC /W:500 /H:260 -->
        <rect x="14.5" y="103.5" rx="0" ry="0" width="141" height="74" style="stroke:NONE; stroke-width:1px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#00B2F8; fill-opacity:1;" />
        <rect x="18.5" y="107.5" rx="0" ry="0" width="114" height="66" style="stroke:NONE; stroke-width:0px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#FFFFFF; fill-opacity:1;" />
        <text class="" x="19.5" y="118.8467" text-anchor="start" style="fill:#444444;font-family:Segoe UI;font-weight:400;font-style:normal;font-size:8.775pt;text-decoration:none;">
            <tspan class="" x="19.5" dy="0">Task</tspan>
        </text>
    </g>
    <rect id="G1_73025cc3-a96c-437d-9029-9abfcded29bd_1" title="" data-pz-guid="73025cc3-a96c-437d-9029-9abfcded29bd" data-pz-type="OT_FUNC" data-pz-shape-id="894a3412-9328-4941-918a-235e0df229bd" data-pz-diagram-id="" class="" onclick="parent.Symbol_Click(this, '73025cc3-a96c-437d-9029-9abfcded29bd');" onmouseover="parent.Symbol_MouseOver(this);" onmouseout="parent.Symbol_MouseOut(this);" x="14.5" y="103.5" width="142" height="74" style="z-index:10002; stroke:#000; stroke-opacity:0.0; fill:#000; fill-opacity:0.0; cursor:pointer;" />
    <g>
        <!-- STX_EV_END /W:500 /H:215 -->
        <rect x="14.5" y="205.5" rx="0" ry="0" width="141" height="61" style="stroke:NONE; stroke-width:0px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#A6A6A6; fill-opacity:1;" />
        <ellipse cx="144.5669" cy="235.9842" rx="7.086614" ry="7.086614" style="shape-rendering:auto; stroke:#FFFFFF; stroke-width:3px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#A6A6A6; fill-opacity:1;" />
        <rect x="18.5" y="209.5" rx="0" ry="0" width="114" height="53" style="stroke:NONE; stroke-width:0px; stroke-linecap:round; stroke-dasharray:; stroke-opacity:1; fill:#FFFFFF; fill-opacity:1;" />
        <text class="" x="19.5" y="220.8467" text-anchor="start" style="fill:#444444;font-family:Segoe UI;font-weight:400;font-style:normal;font-size:8.775pt;text-decoration:none;">
            <tspan class="" x="19.5" dy="0">End</tspan>
        </text>
    </g>
    <rect id="G1_82ed394a-a89c-46db-beb7-c981d6db163f_1" title="" data-pz-guid="82ed394a-a89c-46db-beb7-c981d6db163f" data-pz-type="OTX_EV_END" data-pz-shape-id="9d0036d6-9f08-4930-8c53-403c1206aeb6" data-pz-diagram-id="" class="" onclick="parent.Symbol_Click(this, '82ed394a-a89c-46db-beb7-c981d6db163f');" onmouseover="parent.Symbol_MouseOver(this);" onmouseout="parent.Symbol_MouseOut(this);" x="14.5" y="205.5" width="142" height="61" style="z-index:10003; stroke:#000; stroke-opacity:0.0; fill:#000; fill-opacity:0.0; cursor:pointer;" />
    <g>
        <defs>
            <marker id="defb455676e73d744fe928c357d27b7114a" viewBox="0 0 5 10" refX="5" refY="5" markerUnits="userSpaceOnUse" markerWidth="10" markerHeight="10" orient="90">
                <path d="M 0,0 l 5,5 l -5,5 z" style="fill:#878787; stroke:none; stroke-width:0.0pt;" />
            </marker>
        </defs>
        <polyline fill="none" points=" 85.5,74.5 85.5,103.5" style="stroke:#878787; stroke-opacity:1.0; stroke-width:1pt; stroke-dasharray:; fill:; fill-opacity:;" marker-start="" marker-end="url(#defb455676e73d744fe928c357d27b7114a)" data-pz-shape-id="49166811-fb2a-4ea7-bb30-d6f1bee19906" />
    </g>
```

## Definitions

### SVG
Scalable vector graphics - is an XML-based vector image format for two-dimensional graphics with support for interactivity and animation. The SVG specification is an open standard developed by the World Wide Web Consortium (W3C) since 1999.

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}