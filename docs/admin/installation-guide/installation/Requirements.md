# Preparation

## System requirements

Make sure all system requirements from http://documents.symbioworld.com are fullfilled.

## Software Requirements

* Microsoft SQL Server

For further information about installing MS SQL Server please see here: https://docs.microsoft.com/en-us/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016

Additionally Symbio requires the following software which will be automatically installed by the installation script (###LINK###).

* Internet Information Service
* Net Framework
* Symbio

For version numbers consult http://documents.symbioworld.com.

The following Symbio services are recommended but optional only:

* ![WebJob Scheduler](../../services/web-jobs-scheduler.md)
* ![Rendering Service](../../services/rendering-service/installation-scripted.md)

## User rights

- To install symbio you need a user with the right to install the required software and possibly run powershell as administrator.
- For the symbio application you need a user, who you can enter into the application pool as the executing user. This user needs rights to the target database server including the permission to create databases.

## Database settings

The following database settings are required:
- ALLOW_SNAPSHOT_ISOLATION ON
- READ_COMMITTED_SNAPSHOT ON
