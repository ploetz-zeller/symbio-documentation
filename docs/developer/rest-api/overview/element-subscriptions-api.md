# Element Subscription API

Use this API to access subscriptions for an element in Symbio.

You can access the Swagger definition of these APIs using this URL: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json` - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance.

It is also recommended to use Refit for building corresponding requests. Visit https://github.com/reactiveui/refit for further information.

## Scenarios

- Use the **GET** endpoint to access the subscribers of a given element: `https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Element%20subscriptions%20Api%20(Version%201)/ElementSubscriptionsV1_GetSubscribersOfElement`, e.g.

  ```
  GET https://pz.symbioweb.com/Collection/Storage/_api/v1/subscriptions/f4bacd71-b8fb-48f9-9221-076a98ce8e15?symbio-auth-token=07hke7cywmknzdu7f3fcn64qv1
  ```
