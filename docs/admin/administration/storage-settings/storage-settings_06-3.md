# 6.3 Administration settings - Settings

## 6.3 Settings

### 6.3.1 Facets

In Symbio, facets are used to display processes, organization, repository items, etc. It is possible to set permissions so that only specific user groups can add or edit processes, roles, etc. 

![screen](./media/6.44.png)

### 6.3.2 Variants

Global and local variants are set up via the tile Variants on the administration page.

![screen](./media/6.45.png)

Additionally, the administrator can define tags via the tile Tags to be used together with variants.

### 6.3.3 Tags

Only users with administration rights can create tags. Tags can be used in the user fly out menu to filter processes and repository items in list views (e.g. start page). Existing tags be connected to processes and repository items.

### 6.3.4 Languages

In Symbio, English (1033) and German (1031) are supported. The entire user interface (UI) is localized and the process data culture is activated for both languages. Releasing a process/repository item is only allowed if mandatory attributes are set for both cultures and in case of importing process data only configured cultures will be imported.
English (1033) is the default language.
Other languages can be added as well. It is also possible to remove a language here, except the default language.
Note: If the Symbio installation administrator has activated the translation feature via the Web.config, language-dependent attributes are automatically translated online, whereby the source language corresponds to the set default language. As delivered, the default language is English, i.e. the user can only translate from English to German, but not vice versa.

### 6.3.5 System settings

The following is a short description of the Symbio system settings.

![screen](./media/7.1.png)

#### 6.3.5.1 Disclaimer settings

The disclaimer is disabled in Symbio default settings. 
Activate the checkbox Disclaimer activated to enable the disclaimer in the header bar and press F5 to refresh the Browser window. 
To add a disclaimer text, please use the disclaimer input box.

#### 6.3.5.2 Notifications

Feature to enable the following notifications. Customized mail template text can be configured.

Example for notification - notification after creating a feedback:

![screen](./media/7.2.png)

![screen](./media/7.3.png)

#### 6.3.5.3 Outgoing E-mail settings

Outgoing email settings need to be configured to make use of email task/request notifications. Mandatory fields are highlighted. Nevertheless, username and password for a mail server account should be used under Authentication instead of using an anonymous authentication mode.
Example:

![screen](./media/7.4.png)

#### 6.3.5.4 Privacy settings

The privacy settings currently consist of two settings which can be disabled if company guidelines require it because of work council or other reasons.

- Request enables the option for users to provide feedback on process elements like main/sub processes and repository items. Even in Viewer mode.

  ![screen](./media/7.5.png)

- Global feedback enables the option to provide general Symbio Web application feedback via survey by using the smiley in header bar.

  ![screen](./media/7.6.png)

  ![screen](./media/7.7.png)

#### 6.3.5.5 Process released notification of external systems

Feature to enable e-mail notifications about tasks. Customized mail template text can be configured.

#### 6.3.5.6 Region settings

The region settings are not set in Symbio default settings so the web server´s regional setting (region and time zone) are used. If regional settings are set, then time stamps in the user interface will reflect these, e.g. in attributes of processes or release tasks. The user can still overwrite these settings by setting user-dependent regional settings in the user’s profile in Symbio users management.

#### 6.3.5.7 Theme settings

The default Symbio theme can be customized by changing the colors of the header and navigation bars. It is also possible to replace the Symbio logo with your own logo.
To activate new theme settings, please press on Compile button and then press F5 to refresh the browser window to make the changes visible. To reset the theme back to the Symbio theme, press the Reset button.
We recommend, for example, embedding the corporate identity only in the productive database in order to make a clear difference to the testing system.

![screen](./media/7.10.png)

#### 6.3.5.8 SAP WPB connection

Feature to enable a plug-in which synchronizes SAP Workforce Performance Builder eLearning items to Symbio training repository objects. If you consider using this plug-in, please contact us.

#### 6.3.5.9 Task notifications

Feature to enable the following notifications about tasks. The notifications are enabled within Symbio and the email setting here has no effect.

- Task notification after completing a feedback
- Task notification after creating a feedback
- Task notification after declining the expiry of an element
- Task notification after declining the release of an element 
- Task notification after evaluating a feedback
- Task notification after expiring an element
- Task notification after negative quality assurance of an element
- Task notification after releasing an element
- Task notification after successful quality assurance of an element
- Task notification after usage of an authentication token
- Task notification before expiring an element
- Task notification before quality assurance of an element
- Task notification before releasing an element
- Task notification on approval of feedbacks
- Task notification on validation of feedbacks

Example for task notification - Task notification after releasing an element:

![screen](./media/7.11.png)