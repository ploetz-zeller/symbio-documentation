# Configure

## Extended Configuration

Additional configuration options are available for the administrator in the tile "extended configuration". This includes hiding various information, renaming the standard interface and adding new attributes. 

To use the advanced configuration, please proceed as follows:
- In the admin area, open the tile 'Advanced configuration'

  ![screen](../media/extended_config.png)

- Create a new type with one of the configuration options

  ![screen](../media/tooltip.png)

The next sections describe some of the configurations in more detail.

### Hide

To apply all changes, the configuration has to be activated and applied afterwards.

![screen](../media/hide.png)

#### Hide graphic options

The configuration "Hide graphics options" allows the administrator to minimize the graphical selection in processes. All standard graphics in Symbio and the user-defined fact sheets can be managed with this configuration. 

1. Select type „Hide graphics options“
2. Enter name for configuration entry (e.g. detailed view Sub Process)
3. Define settings 
4. Activate configuration entry

      ![screen](../media/hide_graphic_options1.png)

      ![screen](../media/hide_graphic_options2.png)

5. Apply changes (this only works for configuration entries which are activated in the Detail Content; all configuration entries are always applied).

      ![screen](../media/hide_graphic_options3.png)

#### Collapse views

With this configuration, individual areas such as Detail Content or the navigation tree can be collapsed for Viewer and/or Editor.

![screen](../media/collapsviews1.png)

![screen](../media/collapsviews2.png)

#### Hide attributes

The configuration Hide attributes allows you to delete content in the Detail Content, e. g. 'Risk assessment'.

![screen](../media/hide_attributes.png)

#### Hide referenced objects

The configuration Hide referenced objects you can hide certain elements you do not need for modeling.
Example: Hide 'Requirements' in Detail Content 

1.	Create configuration entry with meaningful name (e.g. Requirements DC)
2.	Define settings: Valid for facet= requirements; valid for type= requirements

      ![screen](../media/hide_ref_objects.png)

3. Check Activate
4. Apply changes

#### Hide global groups

Hides complete groups, e.g. 'Responsible Role', in detail Content.
Hiding can be done for all users or only for the viewer mode.

#### Hide navigation element

Entire navigation elements can be hidden. These include e.g. systems 
or input/output.

![screen](../media/hide_nav_element.png)

### Rename

The administrator renames the information names using this configuration. The new name replaces the selection and is now used throughout the system. 
You can also use this function to rename user attribute groups.

![screen](../media/rename1.png)

![screen](../media/rename2.png)

### Add

1. The Administrator can set up user-defined attributes.

      ![screen](../media/add1.png)

2. In Detail Content, the administrator can select the element types to which the user-defined attribute is to be added. 
Multiple selection allows you to assign the configured attributes to the required types.

      ![screen](../media/add2.png)

3. To any of the new configurated attributes there is the possibility to add “tooltips” to describe the attribute or give hints. The administrator can also use "edit custom attributes" to add the user-defined attributes to the editing of released elements. Thus the user-defined attributes for released attributes can be changed afterwards without versioning. These changes are displayed in the lifecycle.
The following user-defined attribute groups are available:

      ![screen](../media/add3.png)

      User-defined attribute groups can be renamed using the configuration option Rename.

      ![screen](../media/add4.png)

4. By activating “Hide for Viewer” this custom attribute will only be displayed for the editors

5. By activating “Available for reporting” the custom attribute will be analyzed in the estandard reports as well. If this is not activated, this attribute won´t be a part of the reporting

6. By activating “language independent”, this attribute will be for every language and can´t be translated.

7. To apply all changes, the configuration has to be activated and applied afterwards.

      ![screen](../media/add5.png)

Here, there are some examples explained in detail:

#### Add single line attribute

1. Select attribute type 

2. Define ID and set up configuration entry via New.
Defining the ID in capital letters determines the last part of the API name.
Please do not use special characters or '-'.

      ![screen](../media/add_single_line1.png)

      The API name for reusing in for example manuals would then be:
'ATX_CUSTOM_SHORT_DESCRIPTION'

3. Define settings in the Detail Content 
Check the chapter 6.20.3 Add for the details

      ![screen](../media/add_single_line2.png)

      Name: must be maintained in all languages. You can use the Translate button

      Tool Tip: if maintained the attribute will appear with an info symbol and a note when using the mouse over.
      Sorting: if there are several user-defined attributes per user group, the order can be determined here.

      Activate: must be checked; otherwise the attribute is not considered when changes are applied.

      Settings: Valid for facet, valid for type, group, language independent, maximal length.

#### Add selection list attribute

In addition, the following is to be observed here:
- Language independent should be checked
- Apply the changes bevor assigning values

#### Add selection list value attribute

In addition, the following is to be observed here:
- When a new value attribute is created (ID is VALUE) the API name AVTX_CUSTOM_VALUE 
- The selection list attribute must be assigned

### Change

By configuring 'Change', the administrator can change settings in Symbio. To apply all changes, the configuration has to be activated and applied afterwards.

![screen](../media/change.png)

#### Make an attribute mandatory

The admin can make any attribute mandatory. For this, the type 'make an attribute mandatory' needs to be selected and in detail content the settings can be defined. After applying this, all user has to manage the mandatory fields. For example you can set a description to mandatory so any author has to fill in a description for the process.

![screen](../media/make_mandatory.png)

#### Make an attribute informative

The administrator can use this extension to store certain content as informative and thus define it as read-only. This means that these contents cannot be edited. For example, systems can be set as write-protected by this configuration and the content can be retrieved from the BCM interface.

#### Change user selection

The admin adjusts the users in Symbio and can activate or deactivate the inheritance of the persons responsible. 
You can also set that only the selected user types are allowed to edit the process.

![screen](../media/change_selection.png)

## Features

Updates and new features will be available in the Symbio Cloud on a continuous basis. Thus, the Symbio version numbers are now omitted.  

As soon as features have been made available you can test the functions and activate or deactivate them yourself. 

NOTE: New features are flagged as deactivated by default. 

There are different 'periods' of features:

- Experimental: this feature is in an experimental stage. It is recommended to use this exclusively in a test environment.
- Preview: the development of this feature is completed, but it is still in a comprehensive internal test phase. Please use only in a test environment.
- Released: this feature is completely tested and finally released. It may be used in a productive environment.

### Activate and deactivate features

Highlight feature in the list and select required value (Deactivated or Activated) in 'Activation' dropdown of Detail Content.

### Is deprecated / Is one way

Features flagged up as 'Is one way' can only be activated. Once the feature is activated, it cannot be deactivated again.

In case a feature is out of use, it is flagged 'Is deprecated'.

## Release cycle 

Individual settings can be made for the release cycle of processes and objects.

First, create a new Type in the list. Then, go to Detail Content and select a type (or types) for which your settings should be applied.

There are following options:

__Option 1:__ 

Set the number of days after which the process receives the state 'Valid' (after release) in field 'Valid from day span'.

__Option 2:__

Activate 'Prohibit direct release' if the workflow should be started in any case. The state 'Released' will then never be selectable in release dialogue.

__Option 3:__

This functionality allows to add further Approvers or Approver groups to the release cycle. Furthermore, the state 'Ready for Approval' is added to the dialog window.

![screen](../media/approver_workflow.png)

The new order of participants of the release cycle will then be: QA (if set) – Approver/Approver group – Responsible. 

Activate your settings by checkbox and click on 'Apply changes' in the toolbar.

## Fact sheets

Please navigate to Fact sheets [here](https://docs.symbioworld.com/admin/administration/fact-sheets/creating-factsheets/).

## Stereotypes

Please navigate to Stereotypes [here](https://docs.symbioworld.com/admin/administration/stereotypes/creating-stereotypes/).

## Manuals

Default manuals are available. Customized manual templates can be added here.

![screen](../media/manuals.png)

## Reporting

Please refer to [Reporting Service](https://docs.symbioworld.com/admin/services/reporting-service/overview/).

## Navigation

With this feature the help function can be specified in the header (question mark icon). 

Create a new Category with a help entry below in the list. Specify the new help entry in the Detail Content, defining your required target and type of help. Then specify the facet and sub type for which it should be applied to and confirm you activation by the checkbox.

Besides, for the Toolbar, you can create an Execute hook button for service hooks and an Open dialog button for an URL. Make your Navigation settings for which facet and type they should be valid and klick on the checkbox to activate. 

## Document Templates

With the document templates you can define templates for certain elements (e.g. processes, documents, risks, requirements, etc.), which the editor then adds content to. The administrator has the function to define the structure and the layout.

To create a template, the option "Document templates" is available in the admin area.

![screen](../media/doc_templates1.png)

![screen](../media/doc_templates2.png)

After the document template has been created, the administrator must define some attributes in Detail Content. These include the author (if not already set), the person responsible, and the assignment. Here the admin defines for which elements the document template may be used. No template can be edited without assignment. 

![screen](../media/doc_templates3.png)

Further content in the detail area is the header and footer of the document. Here the administrator can display attributes such as Page <PAGE> of <NUMPAGES> for the page number. 

The administrator can set up the structure in the template editor. The chapters can be created hierarchically. Sections can be inserted within chapters. In sections, text blocks or blocks for linking properties can be inserted or combined column by column.

![screen](../media/doc_templates4.png)

![screen](../media/doc_templates5.png)

By selecting the text modules, the admin can create an HTML area that can be edited freely. Any text, images and the like can be created here. The text module is identical to the description in Detail Content. 

In the module for linking properties, the administrator can select a property (e.g. name, description, ID) for the element assigned to the document template.

For all chapters, sections or modules, the administrator can set the check mark to "read-only" in the detail content so that the editor cannot edit them or insert new content. 

![screen](../media/doc_templates6.png)

![screen](../media/doc_templates7.png)

After the document template has been created and the structure has been set up, the editor can use this template. However, the template must first be released in a release workflow. A document is available for editing in the editor as soon as the template has been released.

## Validation rules

This functionality allows to set or modify validation rules that are checked by default before the release workflow of a process or object is started.

![screen](../media/validation_rules.png)

The validation rules are based on the BPMN 2.0 methodology but may be activated or deactivated as required. It is also possible to add new validation rules for specific facets, types etc. and to define a corresponding error message.

Please be aware that if the Result type __Error__ is selected, the release workflow cannot be started, whereas a __Warning__ may be ignored via click on the checkbox in the dialog window. 

![screen](../media/validation_rule_settings.png)


## Dynamic attributes 

Custom-designed feature to use dynamic/user-defined attributes in processes. If you consider using those, please contact us.