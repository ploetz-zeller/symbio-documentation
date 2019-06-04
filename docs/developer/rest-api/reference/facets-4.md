# Facets list

**api-version**: 4.0

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
      "displayNames": {
        "1031": "Automatisierung",
        "1033": "Automation"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/automation/views"
    },
    {
      "name": "bestPracticeTasks",
      "displayNames": {
        "1031": "Best practice tasks",
        "1033": "Best practice tasks"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/bestPracticeTasks/views"
    },
    {
      "name": "capability",
      "displayNames": {
        "1031": "Capability",
        "1033": "Capability"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/capability/views"
    },
    {
      "name": "cultures",
      "displayNames": {
        "1031": "Sprachen",
        "1033": "Languages"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/cultures/views"
    },
    {
      "name": "customerjourneystages",
      "displayNames": {
        "1031": "Customer Journey Stages",
        "1033": "Customer journey stages"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/customerjourneystages/views"
    },
    {
      "name": "customerstructure",
      "displayNames": {
        "1031": "Kunden",
        "1033": "Customers"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/customerstructure/views"
    },
    {
      "name": "docContent",
      "displayNames": {
        "1031": "DocContent",
        "1033": "DocContent"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/docContent/views"
    },
    {
      "name": "docTemplates",
      "displayNames": {
        "1031": "Dokumentvorlagen",
        "1033": "Document Templates"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/docTemplates/views"
    },
    {
      "name": "globaltasks",
      "displayNames": {
        "1031": "Task-Repository",
        "1033": "Task repository"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/globaltasks/views"
    },
    {
      "name": "groups",
      "displayNames": {
        "1031": "Gruppen",
        "1033": "Groups"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/groups/views"
    },
    {
      "name": "inputsoutputs",
      "displayNames": {
        "1031": "Inputs/Outputs",
        "1033": "Inputs/Outputs"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/inputsoutputs/views"
    },
    {
      "name": "it",
      "displayNames": {
        "1031": "Systeme",
        "1033": "Systems"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/it/views"
    },
    {
      "name": "knowledge",
      "displayNames": {
        "1031": "Dokumente",
        "1033": "Documents"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/knowledge/views"
    },
    {
      "name": "kpi",
      "displayNames": {
        "1031": "Kennzahlen",
        "1033": "Key Performance Indicators"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/kpi/views"
    },
    {
      "name": "learning",
      "displayNames": {
        "1031": "Lernen",
        "1033": "Learning"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/learning/views"
    },
    {
      "name": "locations",
      "displayNames": {
        "1031": "Standorte",
        "1033": "Locations"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/locations/views"
    },
    {
      "name": "measures",
      "displayNames": {
        "1031": "Maßnahmen",
        "1033": "Measures"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/measures/views"
    },
    {
      "name": "milestones",
      "displayNames": {
        "1031": "Meilensteine",
        "1033": "Milestones"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/milestones/views"
    },
    {
      "name": "organization",
      "displayNames": {
        "1031": "Organisation",
        "1033": "Organization"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/organization/views"
    },
    {
      "name": "overviewpages",
      "displayNames": {
        "1031": "Übersichtsseiten",
        "1033": "Overview pages"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/overviewpages/views"
    },
    {
      "name": "permissionsets",
      "displayNames": {
        "1031": "Berechtigungsstufen",
        "1033": "Permission sets"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/permissionsets/views"
    },
    {
      "name": "personas",
      "displayNames": {
        "1031": "Personas",
        "1033": "Personas"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/personas/views"
    },
    {
      "name": "processes",
      "displayNames": {
        "1031": "Prozesse",
        "1033": "Processes"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/processes/views"
    },
    {
      "name": "products",
      "displayNames": {
        "1031": "Produkte",
        "1033": "Products"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/products/views"
    },
    {
      "name": "projects",
      "displayNames": {
        "1031": "Projekte",
        "1033": "Projects"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/projects/views"
    },
    {
      "name": "reportsources",
      "displayNames": {
        "1031": "Reporting",
        "1033": "Reporting"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/reportsources/views"
    },
    {
      "name": "requirements",
      "displayNames": {
        "1031": "Anforderungen",
        "1033": "Requirements"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/requirements/views"
    },
    {
      "name": "risks",
      "displayNames": {
        "1031": "Risiken",
        "1033": "Risks"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/risks/views"
    },
    {
      "name": "roles",
      "displayNames": {
        "1031": "Rollen",
        "1033": "Roles"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/roles/views"
    },
    {
      "name": "saleschannels",
      "displayNames": {
        "1031": "Vertriebskanäle",
        "1033": "Sales channels"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/saleschannels/views"
    },
    {
      "name": "search",
      "displayNames": {
        "1031": "Suche",
        "1033": "Search"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/search/views"
    },
    {
      "name": "stakeholders",
      "displayNames": {
        "1031": "Stakeholders",
        "1033": "Stakeholders"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/stakeholders/views"
    },
    {
      "name": "standards",
      "displayNames": {
        "1031": "Normen",
        "1033": "Standards"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/standards/views"
    },
    {
      "name": "stereotypes",
      "displayNames": {
        "1031": "Stereotypen",
        "1033": "Stereotypes"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/stereotypes/views"
    },
    {
      "name": "strategy",
      "displayNames": {
        "1031": "Strategie",
        "1033": "Strategy"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/strategy/views"
    },
    {
      "name": "tags",
      "displayNames": {
        "1031": "Tags",
        "1033": "Tags"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/tags/views"
    },
    {
      "name": "touchpoints",
      "displayNames": {
        "1031": "Touch Points",
        "1033": "Touch Points"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/touchpoints/views"
    },
    {
      "name": "transactions",
      "displayNames": {
        "1031": "Applikations-Services",
        "1033": "Application services"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/transactions/views"
    },
    {
      "name": "usergroups",
      "displayNames": {
        "1031": "Benutzergruppen",
        "1033": "User groups"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/usergroups/views"
    },
    {
      "name": "users",
      "displayNames": {
        "1031": "Benutzer",
        "1033": "User"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/users/views"
    },
    {
      "name": "voiceofcustomers",
      "displayNames": {
        "1031": "Voice of Customers",
        "1033": "Voice of customers"
      },
      "views": "https://demo.symbioworld.com/GIT/ProcessPortalExport/DB02/_api/rest/facets/voiceofcustomers/views"
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
