# Introduction to SAP Solution Manager Connector

In this article it is explained what is SAP Solution Manager Connector service, what are its core functionalities.

## Introduction   

SAP Solution Manager Connector service is a tool that does the data synchronization between Symbio and SAP Solution Manager applications. The synchronization is possible in both ways, from SAP Solution Manager to Symbio and from Symbio to SAP Solution Manager, but it not bidirectional and it follows certain synchronization rules. Although the service itself can run independently, it has to be configured in Symbio in order for someone to use it.

## Features overview

In this section, main features of the service are explained:

1. **Synchronize processes for SAP Solution Manager to Symbio**

    It is possible to synchronize process structure from SAP Solution Manager to Symbio. Users are able to select a SAP Solution Manager scope, and synchronize it to Symbio. When synchronizing scope some library elements that are connected to the structure or diagram elements will also be synchronized. It is possible to do a synchronization of user processes that are created in SAP Solution Manager and also the best practice template processes.

2. **Synchronize Library elements from SAP Solution Manager to Symbio**

    SAP Solution Manager library elements such as *Logical Component Groups*, *Process Step Originals*, *Executable* and *Documents* can be synchronized to Symbio. This kind of synchronization is independent from the Scope synchronization, so one can choose wether to synchronize Processes, Library elements or both.

3. **Synchronize Symbio process to SAP Solution Manager**

    SAP Solution Manager connector can synchronize Symbio process structure to SAP Solution Manager. Unlike the Scope synchronization from SAP Solution Manager, here it is only possible to synchronize a single Symbio subprocess with its hierarchy in one synchronization. Users can synchronize subprocess manually or it can be synchronized on every release in Symbio.

4. **Document synchronization**

    It is possible to synchronize document from SAP Solution Manager to Symbio, and from Symbio to SAP Solution Manager. More details about the document synchronization can be seen here. {Link to documents}


