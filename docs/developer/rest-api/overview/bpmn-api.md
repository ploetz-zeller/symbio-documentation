# BPMN API

Use this API to generate BPMN files for given processes.

You can access the Swagger definition of these APIs using this URL: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance.

It is also recommended to use Refit for building corresponding requests. Visit https://github.com/reactiveui/refit for further information.

## Scenarios

- Use the **GET** endpoint to create a BPMN XML definition for a given process-element: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/BPMN%20Api%20(Version%201)/BpmnV1_Export, e.g.
  ```
  GET https://pz.symbioweb.com/Collection/Storage/_api/v1/bpmn/f4bacd71-b8fb-48f9-9221-076a98ce8e15?lcid=0&symbio-auth-token=07hke7cywmknzdu7f3fcn64qv1
  ```

- Use the **POST** endpoint to import the BPMN which is posted to this endpoint: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/BPMN%20Api%20(Version%201)/BpmnV1_Export, e.g.

    ```
    POST https://pz.symbioweb.com/Collection/Storage/_api/v1/bpmn/f4bacd71-b8fb-48f9-9221-076a98ce8e15?lcid=0&symbio-auth-token=07hke7cywmknzdu7f3fcn64qv1
    ```
