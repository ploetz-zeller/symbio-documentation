# Introduction

The Rendering Service provides HTTP endpoints to request rendered versions of combined SVG/HTML source code.
The service is stateless, does not save data to the disk or any database system.
Currently, only the rendering of PNG files is supported.

## Endpoints

```
POST https://localhost:3334/png
```
The request body is expected to contain the SVG/HTML text.

The response body will contain the rendered PNG as an image/png byte stream.

## Usage in Symbio

In Symbio pick Rendering Service Settings under System Settings
and enter the endpoint URL the service has been installed to.
If the default has been used the URL will be https://localhost:3334/png.
If you instead installed the service to (e.g.) https://shared-host.local:8443/rendering,
the endpoint URL will be https://shared-host.local:8443/rendering/png.

# Requirements

- .NET Framework 4.6.2 installed
- The following operating systems are supported:
  - Windows 7 and newer
  - Windows Server 2008 R2 and newer
- A (dedicated) service user account with local login privileges (a standard user account without remote access will suffice)
- A URL reservation for the service where it can listen for requests; we will describe how to create such a reservation below, you just need to decide on:
  - host name
  - port