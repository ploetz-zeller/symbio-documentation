# Facets list

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
| output | [OperationResultOutput](#operationresultoutput) | The result output. |
| type | [OperationResultType](#operationresulttype) | The result type. |
| data | [OperationError](#operationerror) | The list of errors. |

## Examples

### Get the list of facets

#### Request
```
POST https://demo.symbioworld.com/pz/showcase/_api/rest/facets/
```

#### Response (200 OK)
```json
{
    "count": 41,
    "values": [
        {
            "name": "automation",
            "displayName": "Automation",
            "views": "https://localhost/pz/showcase/_api/rest/facets/automation/views"
        },
        {
            "name": "bestPracticeTasks",
            "displayName": "Best practice tasks",
            "views": "https://localhost/pz/showcase/_api/rest/facets/bestPracticeTasks/views"
        },
        {
            "name": "capability",
            "displayName": "Capability",
            "views": "https://localhost/pz/showcase/_api/rest/facets/capability/views"
        },
        {
            "name": "cultures",
            "displayName": "Languages",
            "views": "https://localhost/pz/showcase/_api/rest/facets/cultures/views"
        },
        {
            "name": "customerjourneystages",
            "displayName": "Customer journey stages",
            "views": "https://localhost/pz/showcase/_api/rest/facets/customerjourneystages/views"
        },
        {
            "name": "customerstructure",
            "displayName": "Customers",
            "views": "https://localhost/pz/showcase/_api/rest/facets/customerstructure/views"
        },
        {
            "name": "docContent",
            "displayName": "DocContent",
            "views": "https://localhost/pz/showcase/_api/rest/facets/docContent/views"
        },
        {
            "name": "docTemplates",
            "displayName": "Document Templates",
            "views": "https://localhost/pz/showcase/_api/rest/facets/docTemplates/views"
        },
        {
            "name": "globaltasks",
            "displayName": "Task repository",
            "views": "https://localhost/pz/showcase/_api/rest/facets/globaltasks/views"
        },
        {
            "name": "groups",
            "displayName": "Groups",
            "views": "https://localhost/pz/showcase/_api/rest/facets/groups/views"
        },
        {
            "name": "inputsoutputs",
            "displayName": "Inputs/Outputs",
            "views": "https://localhost/pz/showcase/_api/rest/facets/inputsoutputs/views"
        },
        {
            "name": "it",
            "displayName": "Systems",
            "views": "https://localhost/pz/showcase/_api/rest/facets/it/views"
        },
        {
            "name": "knowledge",
            "displayName": "Documents",
            "views": "https://localhost/pz/showcase/_api/rest/facets/knowledge/views"
        },
        {
            "name": "kpi",
            "displayName": "Key Performance Indicators",
            "views": "https://localhost/pz/showcase/_api/rest/facets/kpi/views"
        },
        {
            "name": "learning",
            "displayName": "Learning",
            "views": "https://localhost/pz/showcase/_api/rest/facets/learning/views"
        },
        {
            "name": "locations",
            "displayName": "Locations",
            "views": "https://localhost/pz/showcase/_api/rest/facets/locations/views"
        },
        {
            "name": "measures",
            "displayName": "Measures",
            "views": "https://localhost/pz/showcase/_api/rest/facets/measures/views"
        },
        {
            "name": "milestones",
            "displayName": "Milestones",
            "views": "https://localhost/pz/showcase/_api/rest/facets/milestones/views"
        },
        {
            "name": "organization",
            "displayName": "Organization",
            "views": "https://localhost/pz/showcase/_api/rest/facets/organization/views"
        },
        {
            "name": "overviewpages",
            "displayName": "Overview pages",
            "views": "https://localhost/pz/showcase/_api/rest/facets/overviewpages/views"
        },
        {
            "name": "permissionsets",
            "displayName": "Permission sets",
            "views": "https://localhost/pz/showcase/_api/rest/facets/permissionsets/views"
        },
        {
            "name": "personas",
            "displayName": "Personas",
            "views": "https://localhost/pz/showcase/_api/rest/facets/personas/views"
        },
        {
            "name": "processes",
            "displayName": "Processes",
            "views": "https://localhost/pz/showcase/_api/rest/facets/processes/views"
        },
        {
            "name": "products",
            "displayName": "Products",
            "views": "https://localhost/pz/showcase/_api/rest/facets/products/views"
        },
        {
            "name": "projects",
            "displayName": "Projects",
            "views": "https://localhost/pz/showcase/_api/rest/facets/projects/views"
        },
        {
            "name": "reportsources",
            "displayName": "Reporting",
            "views": "https://localhost/pz/showcase/_api/rest/facets/reportsources/views"
        },
        {
            "name": "requirements",
            "displayName": "Requirements",
            "views": "https://localhost/pz/showcase/_api/rest/facets/requirements/views"
        },
        {
            "name": "risks",
            "displayName": "Risks",
            "views": "https://localhost/pz/showcase/_api/rest/facets/risks/views"
        },
        {
            "name": "roles",
            "displayName": "Roles",
            "views": "https://localhost/pz/showcase/_api/rest/facets/roles/views"
        },
        {
            "name": "saleschannels",
            "displayName": "Sales channels",
            "views": "https://localhost/pz/showcase/_api/rest/facets/saleschannels/views"
        },
        {
            "name": "search",
            "displayName": "Search",
            "views": "https://localhost/pz/showcase/_api/rest/facets/search/views"
        },
        {
            "name": "stakeholders",
            "displayName": "Stakeholders",
            "views": "https://localhost/pz/showcase/_api/rest/facets/stakeholders/views"
        },
        {
            "name": "standards",
            "displayName": "Standards",
            "views": "https://localhost/pz/showcase/_api/rest/facets/standards/views"
        },
        {
            "name": "stereotypes",
            "displayName": "Stereotypes",
            "views": "https://localhost/pz/showcase/_api/rest/facets/stereotypes/views"
        },
        {
            "name": "strategy",
            "displayName": "Strategy",
            "views": "https://localhost/pz/showcase/_api/rest/facets/strategy/views"
        },
        {
            "name": "tags",
            "displayName": "Tags",
            "views": "https://localhost/pz/showcase/_api/rest/facets/tags/views"
        },
        {
            "name": "touchpoints",
            "displayName": "Touch Points",
            "views": "https://localhost/pz/showcase/_api/rest/facets/touchpoints/views"
        },
        {
            "name": "transactions",
            "displayName": "Application services",
            "views": "https://localhost/pz/showcase/_api/rest/facets/transactions/views"
        },
        {
            "name": "usergroups",
            "displayName": "User groups",
            "views": "https://localhost/pz/showcase/_api/rest/facets/usergroups/views"
        },
        {
            "name": "users",
            "displayName": "User",
            "views": "https://localhost/pz/showcase/_api/rest/facets/users/views"
        },
        {
            "name": "voiceofcustomers",
            "displayName": "Voice of customers",
            "views": "https://localhost/pz/showcase/_api/rest/facets/voiceofcustomers/views"
        }
    ]
}
```

## Definitions

### Facet
{!developer/rest-api/reference/models/facet.md!}

### OperationResultOutput
{!developer/rest-api/reference/models/operationresultoutput.md!}

### OperationResultType
{!developer/rest-api/reference/models/operationresulttype.md!}

### OperationError
{!developer/rest-api/reference/models/operationerror.md!}
