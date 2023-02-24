# Symbio API Error Handling

## Code 200 Success

A response with the status code 200 represents a successful communication with the server. This does not apply to the response data and its content.

## Code 400 Bad Request

A Code 400 is a client-side error. For details please check the answer message in the http body.

### Code 401 Unauthorized

Authorization failed. Please contact the administrator for the correct token or check your http header for incorrect data. If you have access to Symbio as an administrator yourself, you can manage the tokens. More information here:
[Authentication mit Tokens](./rest-symbio-auth-token-client-temp-example-documentation/rest-symbio-auth-token-client-temp-example-documentation.md)

### Code 404 Not Found

No connection to this address could be established. Check your uri's. More information about the correct construction of the uri's can be found in the
API references.

In addition, an [HTTP status codes overview](https://de.ryte.com/wiki/HTTP_Status_Code)
