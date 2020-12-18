

# How to set up scheduled library sync

This document contains information on how to set up **SAP Solution Manager** service to run a scheduled library synchronization.

## 1. Using Windows Task Scheduler for on premise installations  

**PREREQUISITES:** 

1. *On premise Symbio* installed.

2. *On premise Solman Connector* service installed and linked to the storage.

3. [PowerShell 7.0.3 or greater](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7.1) installed and configured in the System variable PATH.

4. **Administrator user** for the Windows where the scheduled task is set up.

5. (Optional) Windows computers can be set up to block the external scripts. If this is the case, you have to set the ExecutionPolicy to "Bypass" so the script can be executed. See more information about this process [here](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-7.1).


### 1.1. Use the PowerShell script to set up the scheduled task

1. Take the PowerShell script '*Localinstall-SolMan-SyncTrigger.ps1*' from the *symbio-service-solman-interface* repository (scripts folder).
2. Open the PowerShell console as an Administrator.
3. Navigate to the folder where the script is located.
4. (Optional) Run the command to set the "ExecutionPolicy" to "Bypass" or "Unrestricted".
5. Run the command with the given parameters:
    ```
    ./Localinstall-SolMan-SyncTrigger.ps1
    ```
    **Parameters**:
    * *BaseUri* [Mandatory] - The base Uri of your Solution Manager Connector service instance.
    * *TenantId* [Mandatory] - The tenant id of your Symbio storage.
    * *ExecutionTime* [Mandatory] -The time when you scheduled Library synchronization should be executed.
    * *Daily/Weekly* [Mandatory] - Sets a task to be executed on daily/weekly basis.
    * *DaysOfWeek* [Optional - Only needed if Weekly is selected] - Defines the days of the week of the task execution.

    **Examples**:

    Simple guided run for a daily setup:
    ```
    ./Localinstall-SolMan-SyncTrigger.ps1 -Daily
    ```

    Full command for the daily setup:
    ```
    ./Localinstall-SolMan-SyncTrigger.ps1 -BaseUri "https://symbio-solman-service.net" -TenantId "298c7d61-9050-4ba7-aca9-9740f8c3a630" -ExecutionTime 9:00 -Daily
    ```

    Full command for the weekly setup:
    ```
    ./Localinstall-SolMan-SyncTrigger.ps1 -BaseUri "https://symbio-solman-service.net" -TenantId "298c7d61-9050-4ba7-aca9-9740f8c3a630" -ExecutionTime 9:00 -Weekly -DaysOfWeek Monday,Wednesday,Friday
    ```

    **Update**
    
    It is possible to update your scheduled task if needed. You can just run the script again and when prompted, confirm that you want to recreate the task.

    Alternatively you can script again with the additional argument: **-ForceReinstall**
    
    Example:
    ```
       ./Localinstall-SolMan-SyncTrigger.ps1 -BaseUri "https://symbio-solman-service.net" -TenantId "298c7d61-9050-4ba7-aca9-9740f8c3a630" -ExecutionTime 9:00 -Daily -ForceReinstall
    ```

    **Removal**

    To remove the task just run the script with the argument" **-Remove**

    Example:
    ```
    ./Localinstall-SolMan-SyncTrigger.ps1 -Remove
    ```

### 1.2. Manually set up the scheduled task and use PowerShell script as an action

1. Take the PowerShell script 'Trigger-SolManSync.ps1' from the symbio-service-solman-interface repository (scripts folder).
2. Open the Task Scheduler in Windows, and set up you task.
3. As an Action select: 'Start a program'.
4. Set Program/Script setting to use the provided script.
5. Set arguments to: '-command &{"C:\Scripts\Trigger-SolManSync.ps1" -BaseUri '/*your service url*/' -TenantId '/*your tenant id*/'}'
6. Confirm the action and finalize setting your task.



## 2. Using Azure Logic App for cloud versions

**PREREQUISITES:** 
1. Cloud version of Symbio.
2. Cloud version of Solution Manager Connector service linked to the cloud Symbio storage.

For cloud version of the Solution Manager Connector service, the Schedule mechanism is already included in the Resource Group of the service.

### How to set up the scheduled synchronization

1. On Azure portal, open the Resource Group of the Solution Manager Connector service.
2. Open the resource of type Logic app named 'RunLibrarySync' and **Enable** it.
3. Open the resource of type Storage Account named 'librarysync'.
4. Use the Storage Explorer to open the table 'SyncSchedule'.
5. Add a new row to the table with these necessary columns:

    * PARTITIONKEY: "Sync"
    * ROWKEY: {*your tenant id*}
    * INTERVALHRS: {*set the repeat interval for the task in hours*} (integer value)
    * LASTRUNDATE: null (this column must exist, starting value is null but this value will be updated by the Azure Logic App)

    **Example**

    * PARTITIONKEY: "Sync"
    * ROWKEY: "298c7d61-9050-4ba7-aca9-9740f8c3a630"
    * INTERVALHRS: 24
    * LASTRUNDATE: null


**Update**

To update the scheduled tasks, just change the values in the Storage Account table.

**Deletion**

TO remove the scheduled task, just delete the appropriate row in the Storage Account table.


