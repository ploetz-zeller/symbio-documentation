# Best Practice Tasks and Applications

This article will explain you what are the System Applications and Best Practice Tasks and how are they relevant to Solution Manager synchronization.

***
## System - Application

Applications are the Symbio equivalent to Solution Managers, *Logical Component Groups*. All the *Logical Component Groups* for the selected 
Solution Managers Solution, will be imported in Symbio on the ***Linking process***. After they are imported in Symbio, these elements are readonly
and cannot be deleted or modified.

These elements can be reimported manually by clicking the ***Synchronize best practice tasks*** in the Processes architecture view, under the SAP menu.

***
## Best Practice Tasks

All the *Process Steps* from Solution Manager are imported to Symbio on the ***Linking process***. They are imported as **Best Practice Tasks**, 
and after the import they are readonly. **Best Practice Tasks** are connected to the System-**Application**, just like the conection between 
*Process Steps* and *Logical Component Groups* in Solution Manager.
**Best Practice Task**, can be connected to a **Local** or **Global Task** in Symbio. If a **task** is connected to the **Best Practice Task**, it will be
synchronized as a reference to the *Process Step*, otherwise it will be synced as a *draft task*. 

These elements can be reimported manually by clicking the ***Synchronize best practice tasks*** in the Processes architecture view, under the SAP menu.
