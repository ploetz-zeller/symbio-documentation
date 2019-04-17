# Synchronizing documents
---

## Synchronizing documents to SAP Solution Manager

The interface can synchronize documents that are attached to eather main process, sub process or a task in the diagram.
In order to synchronize a document there are several steps to acomplish this:
1. Create a document
2. Attach a document to the elemet in the process structure
3. Synchronize the structure to SAP Solution Manager

### 1.Create a document

You can create a document in the documents facet:

![Test](media/symbioDocument1.png)

There are two attributes you ave to set for the document to be alble to synchronize to SAP Solution Manager.
On the linking action when Symbio storage and SAP Solution Manager branch are linked, all of the documents that are in the scope of the SAP Solution Manager solution of the branch that is being linked will be inserted into symbio like document stereotypes.
They all have the prefix SAP Solution Manager.
You have to choose one of those stereotypes for your document so that it can be synchronized.

![Test](media/symbioDocument2.png)

Then you have to add an attachment to the document.
For now only links to online documents will be synchrnoized, not the physical documents.

![Test](media/symbioDocument3.png)

### 2.Attach a document to the elemet in the process structure

You can synchronize the document attached on the sub, main process and task by attaching the document to it.
![Test](media/symbioDocument4.png)

### 3.Synchronize the structure to SAP Solution Manager

Synchronize the sub process regularly.

In SAP Solution Manager you should see the attached document
