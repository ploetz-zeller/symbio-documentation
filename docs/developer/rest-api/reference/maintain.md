# Maintain

**api-version**: 4.0

Retrieves the list of pools.

```
GET  /_sysadmin/_admin/_api/rest/maintain/{pool}
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| pool | path | false | string | The ID of the pool. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| count | integer | The number of returned values. |
| values | [Pools[]](#pool) | The list of pools. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message. |
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Maintain all available pools

#### Request
```
GET https://demo.symbioworld.com/_sysadmin/_admin/_api/rest/maintain/
```

#### Response (200 OK)
```json
{
    "count": 1,
    "values": [
        {
            "item1": "E5E85FED-BD69-49DF-ADC0-3CA4DAED5305",
            "item2": true
        }
    ]    
}
```


### Example Powershell
```powershell
$headers = @{}
$headers.Add("accept","application/json")
$headers.Add("symbio-auth-token","mytoken")
$result = Invoke-RestMethod -Uri https://sampleinstance.symbioweb.com/_sysadmin/_admin/_api/rest/maintain/ -Headers $headers -UseBasicParsing
$succeded = $result.values | Where-Object item2 -eq $true
$failed = $result.values | Where-Object item2 -eq $false
if (($failed | measure).Count -gt 0) {
    $failedIds = [string]::Join(', ', ($failed | select -ExpandProperty item1))
    $message = 'The following pools could not successful maintained: ' + $failedIds
    Write-Error $message
}
if (($succeded | measure).Count -gt 0) {
    $succededIds = [string]::Join(', ', ($succeded | select -ExpandProperty item1))
    $message = 'The following pool was successful maintained: ' + $succededIds
    Write-Verbose $message
}

```
## Definitions

### Pool
{!developer/rest-api/reference/models/pool.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
