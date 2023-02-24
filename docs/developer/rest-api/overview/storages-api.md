# Storages API

Use this API to create storages or get a list of storages.

You can access the Swagger definition of these APIs using this URL: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json` - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance.

It is also recommended to use Refit for building corresponding requests. Visit https://github.com/reactiveui/refit for further information.

## Scenarios

- Use the **GET** endpoint to get all storages: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Storages%20Api%20(Version%201)/StoragesV1_Get`, e.g.

  ```
  GET https://pz.symbioweb.com/StorageCollection/TestStorage/_api/v1/storages?symbio-auth-token=07hke7cywmknzdu7f3fcn64qv1
  ```

- Use the **POST** endpoint to create a storage: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Storages%20Api%20(Version%201)/StoragesV1_Create`