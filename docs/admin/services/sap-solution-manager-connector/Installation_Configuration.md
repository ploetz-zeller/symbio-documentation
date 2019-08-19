# SAP Solution Manager Connector Configuration

This document contains information on how to configure Symbio to use **SAP Solution Manager Connector** service.

## Configure Symbio to use the service   

1.  Go to Symbio System Administration home and switch to Editor mode.
2.  Go to the Administration menu, and navigate to the Extended configuration.
3.  Create new *Type for an external system*, and for the settings upload the SAP Solution     Manager **.syex** file from the XmlFiles/Bin folder of the service project (if file is missing run the build.ps1 in XmlFiles to create the file).

    ![Test](media/extConf1.PNG)
    ![Test](media/extConf2.PNG)

4.  **Important**: Check the &quot;Activate&quot; checkbox and click on the &quot;APPLY CHANGES&quot; button.
5.  Go to the External Systems page.
6.  Create an new instance of the external system type that you created in Step 3.

    ![Test](media/extSystem1.PNG)

7.  In the Service URL field enter the URL of the SAP Solution Manager Connector micro-service.
8.  In the SAP Solution Manager URL field enter the base URL of the SAP Solution Manager API.
9.  In the Username field enter your username for the SAP Solution Manager API.
10. In the Password field enter your password for the SAP Solution Manager API.
11. If everything is configured correctly you can now select a SAP Solution Manager solution from     the dropdown list.
12. After you have selected the solution,  you can select a branch and the configuration is done.

    ![Test](media/extSystem2.PNG)

13. When you select storage collection, open Admin menu, open External Configuration an click on      the &quot;APPLY CHANGES&quot; button. 
14. Create a Symbio storage. 
15. When storage is created, switch to an Editor mode, open Admin menu, open Features menu, and       enable the BestPracticeTasks feature.  
16. Go back to the storage collection. You can select your SAP Solution Manager external system       for you storage. During this process Symbio will be linked to the micro-service, and auth         token will be created.  

    ![Test](media/Storage.PNG)

17. When linking process is completed, enter the storage, switch to an Editor mode, open Admin        menu, open External Configuration an click on the &quot;APPLY CHANGES&quot; button.




