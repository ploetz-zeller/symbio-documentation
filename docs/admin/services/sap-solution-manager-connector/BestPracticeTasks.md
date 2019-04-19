# Solution Manager Global Elements in Symbio

This article will explain you how are global elements from SAP Solution Manager represented in Symbio and how are they relevant to synchronization.

***
## System - Application (Logical Component Groups)

Applications are the Symbio equivalent to SAP Solution Managers, *Logical Component Groups*. All the *Logical Component Groups* for the selected 
SAP Solution Managers Solution, will be imported in Symbio during the ***Linking process***. After they are imported in Symbio, these elements are readonly
and cannot be deleted or modified.

![Test](media/Applications.png)

These elements can be reimported manually by clicking the ***Synchronize SAP Step Library Objects to Symbio*** in the Processes architecture view, under the SAP menu.

***
## System - Application services (Executables)

Application services are the Symbio equivalent to SAP Solution Managers, *Executables*. All the *Executables* from the
SAP Solution Manager branch or scope, will be imported in Symbio during the ***Linking process***. They are connected to an **Application**, just like *Executable* is connected to *LCG*. After they are imported in Symbio, these elements are readonly and cannot be deleted or modified.

![Test](media/ApplicationServices.png)

These elements can be reimported manually by clicking the ***Synchronize SAP Step Library Objects to Symbio*** in the Processes architecture view, under the SAP menu.

***
## Best Practice Tasks (Process Steps)

All the *Process Steps* from SAP Solution Manager are imported to Symbio on the ***Linking process***. They are imported as **Best Practice Tasks**, 
and after the import they are readonly. **Best Practice Tasks** are connected to the Systems-**Application**, just like the conection between 
*Process Steps* and *Logical Component Groups* in SAP Solution Manager. Also if the *Process step* has a reference to an *Executable*, a **Best Practice Task** has a connection to Systems-**Application service**.
**Best Practice Task**, can be connected to a **Local** or **Global Task** in Symbio. If a **task** is connected to the **Best Practice Task**, it will be
synchronized as a reference to the *Process Step*, otherwise it will be synced as a *draft task*. 

![Test](media/BestPracticeTasks.png)

These elements can be reimported manually by clicking the ***Synchronize SAP Step Library Objects to Symbio*** in the Processes architecture view, under the SAP menu.

***
---

![Test](media/SyncBPTsButton.png)

---
***