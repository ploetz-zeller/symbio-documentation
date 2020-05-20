
# Task reference consolidation rules
---
Synchronization of tasks between Symbio and Solution Manager is a complex operation. Here, all the rules for that synchronization will be described. 
The main point of the consolidation is to keep the consistent state between task references in Symbio in Solution Manager. The users in both systems can changes the references, so the first rule to note is:
**Solution Manager is the owner of the process step references**.

This means that if a task in Solution Manager has a reference, this reference cannot be overridden by the task reference that comes from Symbio.

## Scenario 1:Synchronize task without best practice task to Solution Manager

In Symbio you have an task that doesn't have a best practice task attached.
![Test](media/Scenario1EmptyTaskConsolitation1.png)

You want to synchronize this sub process to Solution Manager.
When the synchronization starts the tasks that do not have the best practice task attached will be provided with a special *Default Process step original*. All the tasks that don't have a best practice task will reference the same *default process step original*.
![Test](media/Scenario1EmptyTaskConsolitation2.png)

Graphical representation of the synchronization:
![Test](media/Scenario1EmptyTaskConsolitation3.png)

From this moment there are two possible cases. 
### Case 1: Symbio user attached a Best practice task to a Task

A user in Symbio attached a Best practice task to a task. Then he synchronizes this to Solution Manager. 
![Test](media/Scenario1EmptyTaskConsolitation4.png)

This will change the task reference on the Solution Manager side.
If again the Best practice task is changed and the synchronization from Symbio to Solution Manager is done, the reference will change.

### Case 2: SAP Solution Manager user attached a Process step original to a Task
Somebody in Solution Manager changes the target of the process step reference and chooses a real process step original instead. 

![Test](media/Scenario1EmptyTaskConsolitation6.png)

![Test](media/Scenario1EmptyTaskConsolitation7.png)

If he want to consolidate this back to Symbio, for now he can click on a "Synchronize SAP Step library Object to Symbio" button that will look for the differences between the references of tasks from Symbio and Solution Manager. If there is difference the reference from Solution Manager will win.


![Test](media/Scenario1EmptyTaskConsolitation8.png)

![Test](media/Scenario1EmptyTaskConsolitation9.png)

Now the task will also have another custom attribute called *SolMan Process step original id*, that stores the id of the SAP Solution Manager reference from the latest consolidation that happened. Now if somebody changes the best practice task attached to the task and tries to synchronize this to Solution Manager, he will fail to do so. Now, when that task has been consolidated, it will not be possible to synchronize change of the reference to Solution Manager. If somebody from SAP Solution Manager changes the reference and consolidates again, this will change the best practice task attached.

**Important notice**

If on both sides the references change, and the user doesn't click the "Synchronize SAP Step library Object to Symbio" button to consolidate the change from Solution manager to Symbio, then when synchronizing from Symbio to Solution Manager the Symbio reference will win. So if the user wants his changes to be consolidated to Symbio, he has to click on the button, or this changes will be lost the next time he synchronizes a sub process from Symbio to Solution Manager.

Also the default process step original will never be consolidated, and will never exist in Symbio. 

## Scenario 2: Synchronize Task with Best practice task to SAP Solution Manager

When a user creates a task and attaches a best practice task to it, and then synchronize that sub process to Solution Manager the task reference will be synchronized to Solution Manager.
Until the user consolidates he can change the reference from Symbio to SAP Solution Manager. Once he has consolidated the change will not be possible from SAP Solution Manager.