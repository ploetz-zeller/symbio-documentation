# Using the REST API from JavaScript

Client-side (i.e. browser-based) JavaScript will most likely use the [Fetch API](https://developer.mozilla.org/en/docs/Web/API/Fetch_API) to access Symbio and will be subject to [HTTP access control aka CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS).

As of today, Symbio allows every origin by responding with the header `Access-Control-Allow-Origin: *`, but does not allow any additional headers, especially `Access-Control-Allow-Headers: symbio-auth-token`. For that reason the authentication token cannot be sent via HTTP headers. Instead it should be sent as part of the query string by appending `?symbio-auth-token=<token>` if no query has been specified yet, or `&symbio-auth-token=<token>` if one already exists in your URL.

## Getting the Storage Info with JavaScript

```js
const url = 'https://example.symbioweb.com/Collection/Database/_api/rest/info';
const tokenQuery = 'symbio-auth-token=<token>';

const response = await fetch(`${url}?${tokenQuery}`, { method: 'POST' });
const info = await response.json();
```