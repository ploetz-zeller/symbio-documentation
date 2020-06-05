# Best practice tasks

Best practice tasks are repository objects belonging to the _Processes_ facet.
By activating this feature, the sub navigation 'best practice tasks' is shown under the _Processes_ facet:

![screen](../media/best_practice_tasks.png)

 Best practice task can be connected to the Task shape in process designer. This is a 1 to 1 relationship, meaning that only one Best practice task is allow to be connected to the one Task.
 When connected to the Task, in the detail content of a Task, user can also see the Application and Application services connected to Best practice task.

Currently Best practice tasks are used by SAP Solution Manager Connector interface and Celonis Importer service.

## Usage of Best practice tasks in SAP Solution Manager Connector interface

 In the use case of SAP Solution Manager interface, Process Step Originals from the connected SAP Solution Manager branch will be imported via the SAP Solution Manager Connector interface. Once imported are available in Symbio and can be referenced to a process Task. Imported Best practice tasks have a stereotype 'SAP Best Practice', they are in a 'Released' and read-only state and therefore editing or removal of such Best practice task is not possible.

For more details, please refer to chapter [SAP Solution Manager Connector](https://docs.symbioworld.com/admin/services/sap-solution-manager-connector/Introduction_Overview/).  

## Usage of Best practice tasks in Celonis Importer

In the use case of Celonis Importer, the Celonis Activities will be imported as a Best practice tasks in Symbio. Once imported are available in Symbio and can be referenced to a process Task. Imported Best practice tasks have a stereotype 'Celonis Activity', they are in a 'In Process' but read-only state. That means that the editing is prohibited, but the removal of these elements is allowed.

For more details, please refer to chapter [Celonis Importer](https://docs.symbioworld.com/admin/services/celonis-importer/usage/).
