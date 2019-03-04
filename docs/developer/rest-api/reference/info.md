# Facets

**api-version**: 1.0

Retrieves the information about the current storage.

```
POST  /{collectionId}/{storageId}/_api/rest/info
```

## Parameters

| Name | In | Required | Type | Description |
|---|---|---|---|---|
| collectionId | path | true | string | The ID of the storage collection. |
| storageId | path | true | string | The ID of the tenant. |

## Responses

### Success 200

| Name | Type | Description |
|---|---|---|
| type | string | The type of the storage: IStorageContext, IStorageCollectionContext or ISysAdminContext. |
| tenant | string | The tenant id of the storage. |
| baseTenat | string | The tenant id of the base storage. |
| template | string | Name of the storage template. |
| dataCultures | string[] | Available data cultures in the storage. |
| defaultDataCulture | string | Default data culture of the storage. |
| isValid | bool | *true* if the storage is valid, otherwise *false*. |
| region | RegionInfo | The configured region in the storage. |
| timeZone | TimeZoneInfo | The configured time zone in the storage. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the info of a BPMN storage

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/info/
```

#### Reponse (200 OK)
```json
{
    "type": "IStorageContext",
    "tenant": "e3f435b3-b1e4-4178-afde-f067027d2113",
    "baseTenant": "0d398b8c-5601-4288-969a-b4eb0d36ffea",
    "template": "Symbio Web Standard (BPMN)",
    "dataCultures": [
        "de-DE",
        "en-US"
    ],
    "defaultDataCulture": "en-US",
    "isValid": true,
    "region": {
        "name": "DE",
        "englishName": "Germany",
        "displayName": "Germany",
        "nativeName": "Germany",
        "twoLetterISORegionName": "DE",
        "threeLetterISORegionName": "DEU",
        "threeLetterWindowsRegionName": "DEU",
        "isMetric": true,
        "geoId": 94,
        "currencyEnglishName": "Euro",
        "currencyNativeName": "Euro",
        "currencySymbol": "€",
        "isoCurrencySymbol": "EUR"
    },
    "timeZone": {
        "Id": "W. Europe Standard Time",
        "DisplayName": "(UTC+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna",
        "StandardName": "W. Europe Standard Time",
        "DaylightName": "W. Europe Daylight Time",
        "BaseUtcOffset": "01:00:00",
        "AdjustmentRules": [
            {
                "DateStart": "0001-01-01T00:00:00",
                "DateEnd": "9999-12-31T00:00:00",
                "DaylightDelta": "01:00:00",
                "DaylightTransitionStart": {
                    "TimeOfDay": "0001-01-01T02:00:00",
                    "Month": 3,
                    "Week": 5,
                    "Day": 1,
                    "DayOfWeek": "Sunday",
                    "IsFixedDateRule": false
                },
                "DaylightTransitionEnd": {
                    "TimeOfDay": "0001-01-01T03:00:00",
                    "Month": 10,
                    "Week": 5,
                    "Day": 1,
                    "DayOfWeek": "Sunday",
                    "IsFixedDateRule": false
                },
                "BaseUtcOffsetDelta": "00:00:00"
            }
        ],
        "SupportsDaylightSavingTime": true
    }
}
```

## Definitions

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
