# Introduction

## About this documention

This Symbio documentation describes Symbio tasks and activities which can be only executed by users who have the application role “Administrator” in Symbio. 

Administrators get useful information about the installation and administration of Symbio and learn more about all available features and services.

It applies to the standard version of Symbio. Personlized customer configurations may differ in contents and visually from the functionality and options described in this documentation.  

## Before you start

All documents such as the system requirements and the operations manual can be found at <https://www.symbioworld.com/en/services/wissen-2/>. 

## Support

Please visit our support website <http://support.symbioworld.com/hc/de> in case of questions, demands and issues.

## Dos and Don'ts in Symbio

Generally specific admin tasks like configurable system settings, e.g. Document template, mail settings, theme settings can be executed with low risk. If mail settings are incorrectly configured, then these settings can be fixed without any downtime.  

### Dos

Generally specific admin tasks like configurable system settings, e.g. Document template, mail settings, theme settings can be executed with low risk. If mail settings are incorrectly configured, then these settings can be fixed without any downtime.  

#### Import/Export (Data Migration)

- First always import a test import into a sandbox database.
- Use the Excel mass data export/import for translations. New objects will not be generated. If a released/expired version already exists, a new version will be generated. 
- Use the Excel-Importer to import from data from other systems, for example. The import includes only newly generated objects or refreshes of objects and does not include the deleting of objects.
NOTE: in order to obtain a satisfactory result, we strongly recommend to consider the Excel import/export exclusively as a project and to perform it only with the help of our support.
- How attributes are refreshed can be configured (OVERRIDE, RETAIN or APPEND); how relations are refreshed can be configured, too (PredecessorSupportsMultipleSuccessors, SuccessorSupportsMultiplePredecessors and SuccessorDeleteDifferentOldPredecessors) 
- Elements which are NOT imported again by a new import will get the status “expired “
- Deletions and Merges must be done manually using the import log
- Please also see Setup Configuration for Excel-Import 
- Update-Imports need an identifier which identifies objects even after there have been name changes, e.g. if an organizational unit is changed; it must be possible to maintain the attribute at the version container (AT_ID) 

### Don'ts

We currently do not recommend executing the following tasks:

#### Import

- Do not import ARIS data if import data already exists in target storage due to consolidation issues, especially with master data.
- Do not import more than single file. Parallel imports increase import time and might run into issues 
    - Symbio Data import (SYMX) 
    - ARIS data (XML)
    - BPMN import (XML)
    - Massdata import (XLSX) of the same type, e.g. Roles by Admin1 and Roles by Admin2 
    - Massdata import (XLSX) of different types
- Do not import the same processes a second time. After the first import they should only be edited in the target Symbio directly. 
- Do not import Symbio Data (SYMX) files if the source databases contain process house/default categories and the target database already has such data. The target database must be empty. An export of process house and categories is impossible since version 5.9.
- Do not import Symbio Data (SYMX) files if the source database is a higher Symbio version than the target database.  
- Do not import Symbio Data (SYMX) files if the source database uses another configuration than the target database.

#### Export

In large databases it’s not recommended to execute the following tasks during business hours:

- Do not export all processes via Massdata because of performance/memory issues on Web server. 

- The Excel-Importer only support files with plain data tables, so it explicitly does not support external data sources, macros, pivot tables or calculated fields/cells.  

- Do not use the Symbio Data export (SYMX) on the Process House or in large categories due to size of exporting data. 

- Do not use the Storage export (SYMX) in Storage Collection due to size of the database.  

#### Feature activation

Before you activate any feature, you have to verify its correct usage in a sandbox database.

#### System settings

Some system settings might affect all users and should be tested in a sandbox database before:


- Do not change SAML settings without any reason if it previously works. Please make use of multiple authentication providers in a sandbox database in same environment before.

#### Consolidation of users and user groups

In Symbio, users and user groups can be consolidated so that all references from one user are transferred to another user or user group. Depending on database size and Symbio version, this can be a very time-consuming step.

- Do not consolidate users or user groups if no regular database backup exists.

- Do not consolidate users or user groups if you didn't perform an user consolidation test in a copy of productive database successfully. 

- Do not consolidate users or user groups referenced in many processes/master data during peak business hours.

## Dos and Don'ts of an Architect

For a for a better understanding, the tasks of a user with the role 'Architect' are as follows:

### Dos

#### Administration of the process architecture
-	Set up and modify categories (including permissions)
-	Create, modify and version main processes
-	Release and expire main processes and sub processes
-	Delete and move main and sub processes within their architecture
#### Administration of objects 
-	Create, modify and version objects in tabular or hierarchical structure
-	Release and expire objects
-	Delete and move objects within their hierarchy
-	Consolidate objects (NOTE: only objects in version 0.1 can be consolidated)
#### Making objects and processes available for releaseChange attributes in released processes without versioning (audit proof)
-	Attributes that can be edited without re-release are: responsible, author, start/end of validity, scope-filter (responsible organizations, locations, tags)
#### Set up Customer Experience Management
-	Create, modify and delete touch points
-	Create, modify and delete sales channels
-	Create, modify and delete stake holders
#### Apply sorting function
#### Create or generate uploaded documents for guidelines / manuals as pdf
#### Maintain ID Provider
#### Clean up processes, objects and hierarchy to keep them up to date
#### Clean up ‘orphaned’ view (should be empty)
#### NOTE: we recommend not to create more than 50 elements per level in hierarchies (processes/objects)

### Don’ts

#### No more than one architect should consolidate objects in the same navigation at the same time, otherwise there is a risk of consolidating objects mutually, which can lead to data inconsistencies
#### No more than one architect should move or delete elements in architectures/hierarchies (of processes or objects) at the same time (e.g. categories or processes/objects that have not yet been released) - under no circumstances should elements be moved in parallel in the same branch. This also applies to moving from the ‘orphaned’ view
#### When deleting subtrees (processes, objects, categories or similar), all child elements should have been deleted or moved before. The same applies to setting the status to ‘expired’
