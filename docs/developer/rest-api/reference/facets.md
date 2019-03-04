---
uid: facets
---
# Facets

**api-version**: 1.0

Retrieves the list of facets.

```
POST  /{collectionId}/{storageId}/_api/rest/facets
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
| count | integer | The number of returned values. |
| values | [Facet[]](#facet) | The list of facets. |

### Error 4xx

| Name | Type | Description |
|---|---|---|
| message | string | The error message. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [Error[]](#error) | The list of errors. |

## Examples

### Get the list of facets

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/
```

#### Reponse (200 OK)
```json
{
    "count": 19,
    "values": [
        {
            "name": "globaltasks",
            "displayName": "Tasks",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/globaltasks/views"
        },
        {
            "name": "inputsoutputs",
            "displayName": "Inputs/Outputs",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/inputsoutputs/views"
        },
        {
            "name": "it",
            "displayName": "IT",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/it/views"
        },
        {
            "name": "knowledge",
            "displayName": "Guidelines",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/knowledge/views"
        },
        {
            "name": "kpi",
            "displayName": "Key Performance Indicators",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/kpi/views"
        },
        {
            "name": "locations",
            "displayName": "Locations",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/locations/views"
        },
        {
            "name": "measures",
            "displayName": "Measures",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/measures/views"
        },
        {
            "name": "milestones",
            "displayName": "Milestones",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/milestones/views"
        },
        {
            "name": "organization",
            "displayName": "Organization",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/organization/views"
        },
        {
            "name": "processes",
            "displayName": "Processes",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/processes/views"
        },
        {
            "name": "requirements",
            "displayName": "Demands/ideas",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/requirements/views"
        },
        {
            "name": "risks",
            "displayName": "Risks",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/risks/views"
        },
        {
            "name": "roles",
            "displayName": "Roles",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/roles/views"
        },
        {
            "name": "standards",
            "displayName": "Standards",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/standards/views"
        },
        {
            "name": "standardtypes",
            "displayName": "Standard Types",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/standardtypes/views"
        },
        {
            "name": "tags",
            "displayName": "Tags",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/tags/views"
        },
        {
            "name": "trainings",
            "displayName": "Trainings",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/trainings/views"
        },
        {
            "name": "transactions",
            "displayName": "Transactions/Services",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/transactions/views"
        },
        {
            "name": "users",
            "displayName": "User",
            "views": "https://demo.symbioworld.com/pz/showcase/_api/rest/facets/users/views"
        }
    ]
}
```

## Definitions

### Facet
{!developer/rest-api/reference/models/facets.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### Error
{!developer/rest-api/reference/models/error.md!}
