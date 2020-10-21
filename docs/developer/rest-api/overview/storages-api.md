# Storages API

Use this API to create storages or get a list of storages.

You can access the Swagger definition of these APIs using this URL: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance.

## Scenarios

- Use the **GET** endpoint to get all storages: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Storages%20Api%20(Version%201)/StoragesV1_Get, e.g.
  ```
  GET https://pz.symbioweb.com/Collection/Storage/_api/v1/permalinks?facetName=Processes&facetViewKey=PersonalizedDiagram&contextKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&variantKey=&versionKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&selectionKey=&routeData[storagecollection]=Collection&routeData[tenant]=Storage&routeData[data]=editor&routeData[lcid]=1033&routeData[controller]=Facet&routeData[action]=Index&routeData[extension]=html&routeData[id]=Processes&routeData[area]=BasePlugin&routeData[routeName]=BasePlugin_default_extension&routeData[preview]=false&routeData[compilationId]=38428a2e-1d92-4aaf-9a19-5586e8087b17&routeData[subId]=treeanddiagram&routeData[renderMode]=Detailed
  ```

- Use the **POST** endpoint to create a storage: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Storages%20Api%20(Version%201)/StoragesV1_Create, e.g.
  ```
  GET https://pz.symbioweb.com/Collection/Storage/_api/v1/permalinks?facetName=Processes&facetViewKey=PersonalizedDiagram&contextKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&variantKey=&versionKey=6ec75354-72f7-4f3b-a002-da8fc7b4d261&selectionKey=&routeData[storagecollection]=Collection&routeData[tenant]=Storage&routeData[data]=editor&routeData[lcid]=1033&routeData[controller]=Facet&routeData[action]=Index&routeData[extension]=html&routeData[id]=Processes&routeData[area]=BasePlugin&routeData[routeName]=BasePlugin_default_extension&routeData[preview]=false&routeData[compilationId]=38428a2e-1d92-4aaf-9a19-5586e8087b17&routeData[subId]=treeanddiagram&routeData[renderMode]=Detailed
  ```