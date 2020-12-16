# Feature Flags API

Use this API to manage Symbio feature flags.

You can access the Swagger definition of these APIs using this URL: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json - replace "pz.symbioweb.com" with the hostname (and port) of your Symbio instance.

It is also recommended to use Refit for building corresponding requests. Visit https://github.com/reactiveui/refit for further information.

## Scenarios

- Use the **GET** endpoint to get all feature flags: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Feature%20flags%20Api%20(Version%201)/FeatureFlagsV1_Get, e.g.
  ```
  GET https://pz.symbioweb.com/StorageCollection/TestStorage/_api/v1/featureflags?symbio-auth-token=07hke7cywmknzdu7f3fcn64qv1
  ```

- Use the **POST** endpoint to activate or deactivate a feature flag: https://pz.symbioweb.com/swagger/index.html?url=/swagger/v1/swagger.json#/Feature%20flags%20Api%20(Version%201)/FeatureFlagsV1_Post, e.g.
  ```
  POST https://pz.symbioweb.com/StorageCollection/TestStorage/_api/v1/featureflags?symbio-auth-token=07hke7cywmknzdu7f3fcn64qv1&id=DigitalDocumentFeature&state=activated
  ```