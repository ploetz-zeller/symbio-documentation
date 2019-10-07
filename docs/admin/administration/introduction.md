# 1 Introduction 

## 1.1 About this document

This document describes Symbio tasks which can be only executed by Symbio users who have the application role “Administrator” in Symbio.  

## 1.2 Before you start

All documents such as the system requirements and the operations manual can be found at <https://www.symbioworld.com/en/services/wissen-2/>. 

## 1.3 Support

Please visit our support website <http://support.symbioworld.com/hc/de> in case of questions, demands and issues.

## 1.4 Do's and Dont's in Symbio

Generally specific admin tasks like configurable system settings, e.g. Document template, mail settings, theme settings can be executed with low risk. If mail settings are incorrectly configured, then these settings can be fixed without any downtime.  

### 1.4.1 Do's

Generally specific admin tasks like configurable system settings, e.g. Document template, mail settings, theme settings can be executed with low risk. If mail settings are incorrectly configured, then these settings can be fixed without any downtime.  

#### 1.4.1.1 Import/Export (Data Migration)

-  First always import a test import into a sandbox database.
-  Use the Excel mass data export/import for translations. New objects will not be generated. If a released/expired version already exists, a new version will be generated. 
-  Use the Excel-Importer to import from data from other systems, for example. The import includes only newly generated objects or refreshes of objects and does not include the deleting of objects.     
     - How attributes are refreshed can be configured (OVERRIDE, RETAIN or APPEND); how relations are refreshed can be configured, too (PredecessorSupportsMultipleSuccessors, SuccessorSupportsMultiplePredecessors and SuccessorDeleteDifferentOldPredecessors) 
    - Elements which are NOT imported again by a new import will get the status “expired “
    - Deletions and Merges must be done manually using the import log
    - Please also see Setup Configuration for Excel-Import 
    - Update-Imports need an identifier which identifies objects even after there have been name changes, e.g. if an organizational unit is changed; it must be possible to maintain the attribute at the version container (AT_ID) 

### 1.4.2 Dont's

We currently do not recommend executing the following tasks:

#### 1.4.2.1 Import

- Do not import ARIS data if import data already exists in target storage due to consolidation issues, especially with master data.
-  Do not import more than single file. Parallel imports increase import time and might run into issues 
    - Symbio Data import (SYMX) 
    - ARIS data (XML)
    - BPMN import (XML)
    - Massdata import (XLSX) of the same type, e.g. Roles by Admin1 and Roles by Admin2 
    - Massdata import (XLSX) of different types
- Do not import the same processes a second time. After the first import they should only be edited in the target Symbio directly. 
- Do not import Symbio Data (SYMX) files if the source databases contain process house/default categories and the target database already has such data. The target database must be empty. An export of process house and categories is impossible since version 5.9.
- Do not import Symbio Data (SYMX) files if the source database is a higher Symbio version than the target database.  
- Do not import Symbio Data (SYMX) files if the source database uses another configuration than the target database.

#### 1.4.2.2 Export

In large databases it’s not recommended to execute the following tasks during business hours: 
- Do not export all processes via Massdata because of performance/memory issues on Web server. 
- The Excel-Importer only supports files with plain data tables, so it explicitly does not support external data sources, macros, pivot tables or calculated fields/cells.  
- Do not use the Symbio Data export (SYMX) on the Process House or in large categories due to size of exporting data. 
- Do not use the Storage export (SYMX) in Storage Collection due to size of the database.  

#### 1.4.2.3 Feature activation

Before you activate any feature, you have to verify it's correct usage in a sandbox database.

### 1.4.3 System settings

Some system settings might affect all users and should be tested in a sandbox database before:
- Do not change SAML settings without any reason if it previously works. Please make use of multiple authentication providers in a sandbox database in same environment before.

### 1.4.4 User consolidation

In Symbio, users can be consolidated so that all references from one user are transferred to another user. Depending on database size and Symbio version, this can be a very time-consuming step.
- Do not consolidate users if no regular database backup exists.
- Do not consolidate users if you didn't perform an user consolidation test in a copy of productive database successfully. 
- Do not consolidate users referenced in many processes/master data during peak business hours.

### 1.4.5 User group consolidation

In Symbio, user groups can be consolidated so that all references from one user group are transferred to another user group. Depending on database size and Symbio version, this can be a very time-consuming step.
- Do not consolidate user groups if no regular database backup exists.
- Do not consolidate user groups if you didn't perform an user consolidation test in a copy of productive database successfully. 
- Do not consolidate user groups referenced in many processes/master data during peak business hours.


# Symbio Administration

To enter the configuration area for the Symbio Administrator, please switch into Editor mode and click on the gear icon in the top right corner:

![screen](./media/5.1.png)

The following is a short description of the various administration and configuration possibilities in the administration area.

For Symbio version info, navigate to the bottom of the page. The version number includes the build date, the commit ID and the commit date of last code changes. Please reference to it in case of incidents if on-premise.

![screen](./media/5.2.png)

## Log files

Log files from Symbio application folder can be retrieved here. By default, only errors will be logged. Please contact your Symbio IT Administrator if the logging level needs to be increased to include warnings and informational log messages by changing settings in the Web.config file during downtime.

## Apply new configuration

If the configuration/method (SYTX) has been changed only and the changes are not directly visible, the Admin can force the configuration change here but it should not be necessary.
- By applying the new configuration this also forces to perform Symbio maintenance tasks which may take a while. Don't do it during business hours.

## Generate reporting scripts

SQL Reporting Services Database relevant only. Please contact us if you like to use Reporting within Symbio.
