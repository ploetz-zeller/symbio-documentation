# Introduction

## About this documention

This Symbio documentation describes Symbio tasks and activities which can be only executed by users who have the application role “Administrator” in Symbio. 

Administrators get useful information about the installation and administration of Symbio and learn more about all available features and services.

It applies to the standard version of Symbio. Personlized customer configurations may differ in contents and visually from the functionality and options described in this documentation.  

## Before you start

This section provides minimum system requirements that have to be met in order to make use of the Symbio products.
All user manuals and other assets regarding our products can be found at https://www.symbioworld.com/donwloads

### Symbio system requirements

#### Minimum requirements for client computers

This section provides minimum software requirements for a client computer to work with Symbio.

##### Browser support matrix

We are continuously working on providing the best experience to our users. Using the newest
technology available on the market sometimes requires dropping support for some older browser
versions. The following browsers are currently fully supported:

|Browser | Version|
|--------|--------|
|  Microsoft Edge   |Last two released versions|
|  Mozilla Firefox | Last two released ESR versions|
|  Google Chrome  | Last two released versions|

Symbio also runs on the **Safari/iOS** browser, but this is not tested explicitly.
In August 2020 Microsoft has announced the timeline for the ending support for Internet Explorer 11
(IE 11) across the 365 apps and services. We will follow this procedure and discontinue supporting
**Microsoft's IE 11**.

### Recommended bandwidth ranges

This section provides generally recommended bandwidth ranges.
Bandwidth ranges of 3 megabits per second (Mbps) (dual T1) and greater with latencies no greater
than 250 milliseconds (ms)

### Symbio (OnPrem Installation)

#### Overview

Symbio provides several installation scenarios. Currently, these installations include a single server
with a local SQL Server and a two-server installation with a web server and a database server. This
article describes the hardware and software requirements for Symbio in each of the two scenarios.

**Important:** The information in this article apply to Symbio only. Other listed products in this article
have their own software and hardware requirements. Please contact the manufacturer of the
specified product in order to get more information.

##### Single server installation

_Web server with locale database_

- Web pages
- Local services
- Different plugins for different needs
- Multitenancy
- Local SQL Server database

##### Two server installation

_Web server_

- Web pages
- Local services
- Different plugins for different needs
- Multitenancy

_Database server_

- Hosts the Symbio databases
- Can be mirrored or clustered
- To increase performance and capacity consider adding disks to
the database server or adding database servers (depending on
the bottleneck)

#### Minimum hardware requirements

The values in the following table are minimum values for installations on a single server with a
local database and for web and database servers in a two-server installation.

|Installation scenario | Deployment type and scale| RAM| Processor| Hard disk space|
|--------|--------|--------|--------|--------|
|  **Single server** | Development or evaluation installation| 4GB | 64-bit, 4 cores | 1 GB plus space depending on data|
|  **Single server** | Production deployment| 12GB | 64-bit, 4 cores | 5 GB plus space depending on data|
|  **Two server** - web server | Development or evaluation installation| 1GB | 64-bit, 4 cores | 5 GB plus space depending on data|
|  **Two server** - web server | Production deployment| 12GB | 64-bit, 4 cores | 5 GB plus space depending on data|
|  **Two server** - database server | Development or evaluation installation | 4GB | 64-bit, 4 cores | 1 GB plus space depending on data|
|  **Two server** - database server | Production deployment| 8GB | 64-bit, 4 cores | 5 GB plus space depending on data|

Hard disk space depends on how much content that you have in your deployment.

#### Minimum software requirements for server

This section provides minimum software requirements for each server.
Minimum requirements for database server including local database server in case of single server
deployment (one of the following):

- One of the following
    - 64-bit edition of Microsoft SQL Server 2022 (recommended)
Symbio needs as Collation type "SQL_Latin1_General_CP1_CI_AS".
For more information about requirements please visit https://docs.microsoft.com/en-us/sql/sql-server/install/hardware-and-softwarerequirements-for-installing-sql-server-ver15?view=sql-server-ver15
    - 64-bit edition of Microsoft SQL Server 2019
Symbio needs as Collation type "SQL_Latin1_General_CP1_CI_AS".
For more information about requirements please visit https://docs.microsoft.com/en-us/sql/sql-server/install/hardware-and-softwarerequirements-for-installing-sql-server-ver15?view=sql-server-ver15

        **Deprecated**: 64-bit edition of Microsoft SQL Server 2017
From 3 th Quarter 2023 we won’t support SQL Server 2017 anymore.

        **Deprecated**: 64-bit edition of Microsoft SQL Server 2016 
From 4th Quarter 2022 we won’t support SQL Server 2016 anymore.

        Please note that SQL Server 2016/2017 Express LocalDB or Express Edition is not supported.

Minimum requirements for a web server or single server (one of the following):

- One of the following:
    - 64-bit edition of Windows Server 2022 Standard/Datacenter (recommended)
    - 64-bit edition of Windows Server 2019 Standard/Datacenter
    - 64-bit edition of Windows Server 2016 Standard/Datacenter
    - 64-bit edition of Windows Server 2012 R2 Standard/Datacenter (deprecated)

      _Symbio still runs on Windows Server 2012 R2, if possible, a newer Windows version should be used. Automated installation scripts may cause problems under Windows Server 2012 R2._

- Web Server (IIS) role
- Microsoft .NET Framework version 4.7.2
- For Symbio microservices: Microsoft .NET 6 and 7

### Symbio (OnPrem Installation)

#### Overview

Symbio reporting is important feature of Symbio. Symbio provides number of predefined reports for
users to generate and print. For enabling reporting features, some additional software needs to be
installed and configured. For reporting purposes standard Symbio database cannot be used, and new
ODS Database must be created for reporting. Symbio uses SQL Server Reporting Services for deploying
and generating reports. For end user SQL Server Reporting Services are completely transparent
because reports are fully integrated into Symbio. For ODS database creation Symbio specialized REST
API (RESTful Application Programing Interface) is used by Microservice, which is fetching all data from
Symbio and generating data in ODS database. 

##### Architecture

![Screenshot 2023-11-03 at 13 57 04](https://github.com/lejckn/symbio-documentation/assets/149780442/ff783698-be3d-4287-acf2-51e8524824ff)

#### Minimum software requirements for server

This section provides minimum software requirements for each server.
Minimum requirements for reporting server including local database server in case of single server
deployment:

- One of the following:

    - 64-bit edition of Microsoft SQL Server 2022 **(recommended)**
Symbio needs as Collation type "SQL_Latin1_General_CP1_CI_AS".
For more information about requirements please visit
https://docs.microsoft.com/en-us/sql/sql-server/install/hardware-and-softwarerequirements-for-installing-sql-server-ver15?view=sql-server-ver15

    - 64-bit edition of Microsoft SQL Server 2019 **(recommended)**
Symbio needs as Collation type "SQL_Latin1_General_CP1_CI_AS".
For more information about requirements please visit https://docs.microsoft.com/en-us/sql/sql-server/install/hardware-and-softwarerequirements-for-installing-sql-server-ver15?view=sql-server-ver15
        Deprecated: 64-bit edition of Microsoft SQL Server 2017
        From 3th Quarter 2023 we won’t support SQL Server 2017 anymore.

        **Deprecated**: 64-bit edition of Microsoft SQL Server 2016
      From 4th Quarter 2022 we won’t support SQL Server 2016 anymore.
        Please note that SQL Server 2016/2017 Express LocalDB or Express Edition is not
  supported.


- One of the following:
    - 64-bit edition of Microsoft SQL Server 2022 Reporting Services **(recommended)**
      For more information about requirements please visit https://learn.microsoft.com/en-us/sql/sql-server/install/hardware-and-softwarerequirements-for-installing-sql-server-2022
    - 64-bit edition of Microsoft SQL Server 2019 Reporting Services
      For more information about requirements please visit https://learn.microsoft.com/en-us/sql/sql-server/install/hardware-and-softwarerequirements-for-installing-sql-server-2019

        **Deprecated**: 64-bit edition of Microsoft SQL Server 2017 Reporting Services
    From 3th Quarter 2023 we won’t support SQL Server 2017 Reporting Services anymore.

        **Deprecated**: 64-bit edition of Microsoft SQL Server 2016 Reporting Services
    From 4th Quarter 2022 we won’t support SQL Server 2016 Reporting Services anymore.

        Please note that SQL Server 2016/2017 Express LocalDB or Express Edition with Advanced Services is not supported.

### Single Sign-On/SAML 2.0

Symbio supports SAML 2.0 and the following Identity Providers (IdP):

- Microsoft Active Directory Federation Services (MS ADFS)
- Microsoft Azure Active Directory (MS AAD)
- Ping Identity
- OneLogin.com
  
Other Identity Providers might work because of SAML 2.0 but need to be treated as a separate
project if out-of-the-box configuration does not work.

Please also refer to our online help here:

https://docs.symbioworld.com/admin/installation-guide/saml-configuration/1_introduction/

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

No more than one architect should consolidate objects in the same navigation at the same time, otherwise there is a risk of consolidating objects mutually, which can lead to data inconsistencies

No more than one architect should move or delete elements in architectures/hierarchies (of processes or objects) at the same time (e.g. categories or processes/objects that have not yet been released) - under no circumstances should elements be moved in parallel in the same branch. This also applies to moving from the ‘orphaned’ view

When deleting subtrees (processes, objects, categories or similar), all child elements should have been deleted or moved before. The same applies to setting the status to ‘expired’
