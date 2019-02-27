# Preparation

## System requirements

Make sure all system requirements from http://documents.symbioworld.com are fullfilled.

## Software Requirements

* Microsoft SQL Server

For further information about installing MS SQL Server please see here: https://docs.microsoft.com/en-us/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014

Additionally Symbio requires the following software which will be automatically installed by the installation script (###LINK###).

* Internet Information Service
* Net Framework
* Symbio

For version numbers consult http://documents.symbioworld.com.

The following Symbio services must be installed, either manually or by using the installation script.

* WebJobs Service (http://docs.symbioworld.com/content/Articles/webjobsservice/index.html)
* Rendering Service (http://docs.symbioworld.com/content/Articles/RenderingService/index.html)

## User rights

- To install symbio you need a user with the right to install the required software and possibly run powershell as administrator.
- For the symbio application you need a user, who you can enter into the application pool as the executing user. This user needs rights to the target database server, there he must have the right to create databases.