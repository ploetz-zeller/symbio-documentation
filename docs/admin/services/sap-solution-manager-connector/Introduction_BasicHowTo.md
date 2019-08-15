# Introduction to SAP Solution Manager Connector

The basics of how you can use the SAP Solution Manager Connector service, are explained in the following section.

## How to use interface (basic)

Under *PROCESSES* facet, in the *architecture* view, there is **SAP** menu bar item.

![Test](media/HowToUse1.png)

Under **SAP** menu bar, there are 3 relevant menu items for the SAP Solution Manager Connector:

![Test](media/HowToUse2.png)

1. *Synchronize SAP Step Library Objects to Symbio* button

    This button should be used when you want to synchronize all SAP Solution Manager branch library objects (Process Step Originals, Executables, Roles, Documents) to Symbio. When you click the button, a dialog will appear:

    ![Test](media/HowToUse3.png)

    In this dialog, you can start the synchronization process for the library object.
    There is also some additional information:

    *Last synchronization*: Time of the latest SAP Solution Library object synchronization - Result of the synchronization process

    *Last successful synchronization*: Time of the latest SAP Solution Library objects successful synchronization

    If you do not close the window after synchronization has started, a message with the synchronization result will appear, once the process has finished.

    If synchronization is already in progress, a message will appear and you will not be able to synchronize until the previous process is completed.

2. *Synchronize SAP practice templates* button

    This button should be used when you want to synchronize the SAP Solution Manager processes to Symbio. Along with the process structure, library elements that are connected to the objects in the process structure will also be synchronized. When you click the button, a dialog will appear:

    ![Test](media/HowToUse4.png)

    In this dialog, you must choose a scope that you want to synchronize. If you want to synchronize everything you can use the predefined Scoped named 'Show all'. Once you have selected the Scope you wish to synchronize, you can start the synchronization process.

    There is also some additional information:

    *Last synchronization*: The name of the Scope - Time of the latest SAP Solution Library object synchronization - Result of the synchronization process

    *Last successful synchronization*: The name of the Scope - Time of the latest SAP Solution Library objects successful synchronization

    If you do not close the window after synchronization has started, a message with the synchronization result will appear, once the process has finished.

    If synchronization is already in progress, a message will appear and you will not be able to synchronize until the previous process is completed.

3. *Synchronize subprocess to SAP Solution Manager* button

    When you have selected a subprocess in Symbio, by clicking this button you will trigger the synchronization of that subprocess and its hierarchy to SAP Solution Manager.

    The same effect can be achieved by releasing the subprocess which has the attribute 'Sync on release' set to true:

    ![Test](media/SyncOnRelease.png)


