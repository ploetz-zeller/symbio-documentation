# Synchronizing structure and diagrams from SolMan to Symbio
---
## Mapping of structure elements
The elements are going to e synchronized following the table below:

| SolMan | Symbio |
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

| SolMan | Symbio |
| ------ | ------ |
| events (start,end,intermediary) | appropriate events |
| gateways | appropriate gateways |
| draft task | local task |
| process step reference | local task with appropriate bpt attached |
| empty sub process | interface |

### Synchronizing sub process reference

For the su bprocess reference elements to be synchronized correctly some conditions have to be met:
1 Sub process has to be referenced to the process
2 Sub process reference has to the attached to one diagram, or it can have many but one has to be default

If the sub process reference doesn have a link to a concrete diagram, or it has more diagram attached but no default one the sub process will be synced like an interface ( empty placeholder).
If the conditions are met the sub process reference will be synced like a sub process reference shape.
## Process of synchronization
To synchronize the structrue from SolMan to Symbio go to processes-> architecture and click on the SAP button. Clik on the "Synchronize structure from SolMan to Symbio" button.
![Test](media/SolManSymbio1.PNG)

A dialog will open.
You can choose what scope you want ot sync, or if you leave it empry the whole structure will be synced.
![Test](media/solManSymbio2.PNG)
 When the synchronization is done there will be a new category added to the process house element.The whole synchronized structure will be in this category.
 The elements will be released and not editable. For now you can copy only diagram elements to another structure.