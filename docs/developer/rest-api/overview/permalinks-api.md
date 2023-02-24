# Permalinks API

Use these APIs to work with permanent links to Symbio entities. Possible Symbio entities include:

- Processes
- Specific versions of processes
- Specific selections (e.g. task, event, role) within processes
- Repository elements
- Overview pages

You can access the Swagger definition of these APIs using this URL: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/PermalinksV1` - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance.

## Scenarios

- Use the **GET** endpoint to request information about possible permanent link types and already existing permanent links of an entity: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/PermalinksV1/PermalinksV1_GetPermaLinkInfo`, e.g.

  ```
  GET https://pz.symbioweb.com/Collection/Storage/_api/v1/permalinks?facetName=Processes&facetViewKey=PersonalizedDiagram&contextKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&variantKey=&versionKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&selectionKey=&routeData[storagecollection]=Collection&routeData[tenant]=Storage&routeData[data]=editor&routeData[lcid]=1033&routeData[controller]=Facet&routeData[action]=Index&routeData[extension]=html&routeData[id]=Processes&routeData[area]=BasePlugin&routeData[routeName]=BasePlugin_default_extension&routeData[preview]=false&routeData[compilationId]=38428a2e-1d92-4aaf-9a19-5586e8087b17&routeData[subId]=treeanddiagram&routeData[renderMode]=Detailed
  ```

- Use the **POST** endpoint to get or create a new permanent link of a given type for an entity: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/PermalinksV1/PermalinksV1_GetOrCreatePermaLink`

  ```
  POST https://pz.symbioweb.com/Collection/Storage/_api/v1/permalinks?facetName=Processes&facetViewKey=PersonalizedDiagram&contextKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&variantKey=&versionKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&selectionKey=&routeData[storagecollection]=Collection&routeData[tenant]=Storage&routeData[data]=editor&routeData[lcid]=1033&routeData[controller]=Facet&routeData[action]=Index&routeData[extension]=html&routeData[id]=Processes&routeData[area]=BasePlugin&routeData[routeName]=BasePlugin_default_extension&routeData[preview]=false&routeData[compilationId]=38428a2e-1d92-4aaf-9a19-5586e8087b17&routeData[subId]=treeanddiagram&routeData[renderMode]=Detailed
  JSON body: {"linkType":"ofVersion"}
  ```
