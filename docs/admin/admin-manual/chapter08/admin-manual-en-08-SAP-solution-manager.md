# 8 SAP Solution Manager 7.2 Interface Configuration

## 8.1 Introduction

The SAP Solution Manager 7.2 - Symbio interface allows the synchronization of business processes and their structure between SAP Solution Manager and Symbio application.
Symbio being the business window into the IT world of Solution Manager 7.2. 

![screen](./media/7.12.png)

Solution Manager 7.2 supports the so-called branch management. One branch is a version of business process models, documentation, systems… It also supports the release process, meaning it is possible to release one branch to a higher parent branch. This setup allows you to clearly differentiate between business process content that is productive and content that is still work in progress. The minimum branch setup consists of a production and maintenance branch. Further branches such as development or import branch can be added due to specific requirements. The picture below describes one Solution Manager 7.2 solution and its connection to Symbio. The set of branches are all stored in one container that is called the Solution. The solution it the single source of truth in Solution Manager 7.2.

![screen](./media/7.13.png)

Solution Manager 7.2 also supports reference content. The usage of the SAP reference content is a good possibility to accelerate a project, especially in the prepare and explore phase. The provided content can be downloaded from the Solution Manager to Symbio and be processed there.
An example of the reference content are SAP’s best practice packages that deliver predefined processes for SAP solutions.

## 8.2 Synchronization flow

![screen](./media/7.14.png)

The reference content is imported to the import branch. The user would choose the content from the import branch he wants to transfer to the development branch which will communicate with Symbio. Then the content from the design branch is synchronized to Symbio. In Symbio the business user would be able to change, add and delete content. When he is finished with modeling he would upload the changed content back to the design branch. 

## 8.3 Hierarchical relationship

The hierarchical relationship between Symbio and Solution Manager is shown in the picture below. 

![screen](./media/7.15.png)

Symbio Process house is synchronized with Solution Manager branch. The administrator can configure to which branch the Symbio storage is connected to, on the settings page.

## 8.4 Supported and planned elements

The elements that are supported by the interface can be organized into three groups:

1. Hierarchical elements
- Process house
- Category
- Main Process
- Sub process

2. Business process elements
- Start Event
- End Event
- Intermediary Event
- Local Task
- Global task(from the repository)
- Gateways (Or, Either-or, And)
- Sub Process as a reference to another sub process
- Sub process as placeholder
- Conditions

3. Corona elements
- Roles

Additional elements that are planned to be supported by the standard interface, are the corona elements
- Documents
- Systems
- Transaction
- Additional elements can be added on customer request

## 8.5 Example of the synchronization

![screen](./media/7.16.png)

This example will show the third and fourth step of the picture. The first two steps have already been done in Solution Manager 7.2.

There is a hierarchical structure in the design branch:

![screen](./media/7.17.png)
Hierarchical view Solution Manager

Also the processes have diagrams attached:

![screen](./media/7.18.png)
Diagram view for Solution Manager

When the storage is created in Symbio we have to configure the branch in order to synchronize the content from the design branch. This is done in the Storage settings:

![screen](./media/7.19.png)

When the connection is successful the user can import the content from Solution Manager 7.2 to Symbio.

Navigate to Processes->architecture->SAP to find the 'Synchronize with SAP Solution Manager'-button.

![screen](./media/7.20.png)

When clicking the button, a pop-up screen will appear. By clicking OK the synchronization from Design branch to Symbio will start:

![screen](./media/7.21.png)

The process of the synchronization can be seen on the Info page:

![screen](./media/7.22.png)

After the import ran successfully, the user can navigate back to the process structure and see the imported content.

![screen](./media/7.23.png)

Global tasks are located in Repository -> tasks
![screen](./media/7.24.png)

Lanes are located in Repository -> roles
![screen](./media/7.25.png)

Now the user can add, change or delete the structure in Symbio. 
In this example a task will be added. Also a new role will be attached to this element.

![screen](./media/7.26.png)

![screen](./media/7.27.png)

After the changes are done, the process content can be uploaded back to the Design branch of Solution Manager 7.2. This is done the same way the import was done.
Navigate to Processes->Architecture->SAP-> Synchronize with SAP Solution Manager-> click ok on the pop-up window.

The result of the synchronization can be seen on the Info page.

![screen](./media/7.28.png)

When the synchronization was successful you can compare the structure and the diagrams.

![screen](./media/7.29.png)