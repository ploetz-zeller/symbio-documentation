# Synchronizing structure and diagrams from SAP Solution Manager to Symbio
---
## Mapping of structure elements
The elements are going to e synchronized following the table below:

| SAP Solution Manage | Symbio |
| ------ | ------ |
| Folder | Category |
| Scenario | Main Process |
| Process | Main Process |
| Diagram a | SubProcess A |
| Diagram b | SubProcess B |
| Diagram c | SubProcess C |

This way, if the process has multiple diagrams, all of them will be synchronized.

## Synchronizing diagram elements

The diagram will be synced if the type is Process or Collaboration but only with one original pool.
The diagram will be synced if the sub type is **"By Role"**, and if the sub type is **"By System"** the diagram will not be synchronized.

| SAP Solution Manage | Symbio |
| ------ | ------ |
| events (start,end,intermediary) | appropriate events |
| gateways | appropriate gateways |
| draft task | local task |
| process step reference | local task with appropriate bpt attached |
| empty sub process | interface |

### Synchronizing sub process reference

For the sub bprocess reference elements to be synchronized correctly some conditions have to be met:
1 Sub process has to be referenced to the process
2 Sub process reference has to the attached to one diagram, or it can have many but one has to be default

If the sub process reference doesn have a link to a concrete diagram, or it has more diagram attached but no default one the sub process will be synced like an interface ( empty placeholder).
If the conditions are met the sub process reference will be synced like a sub process reference shape.
## Process of synchronization
To synchronize the structure from SAP Solution Manage to Symbio go to processes-> architecture and click on the SAP button. Click on the "Synchronize best practice package" button.
![Test](media/SolManSymbio1.png)

A dialog will open.
You can choose what scope you want to sync, or if you leave it empty the whole structure will be synced.
![Test](media/solManSymbio2.png)
 When the synchronization is done there will be a new category added to the process house element.The whole synchronized structure will be in this category.
 The elements will be released and not editable. For now you can copy only diagram elements to another structure.

 If a synchronized *Task* has an attached *Best Practice Task*, the *Application* and *Application service* that are attached to that *Best Practice Task* are also visible in the detail content of the *Task*:

![Test](media/ConnectedApplications.png)
 