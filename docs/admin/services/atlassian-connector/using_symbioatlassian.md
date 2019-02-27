# Using the Symbio to Atlassian

## Prerequisites for the Symbio to Atlassian interface
- The external system for the interface must be loaded on _sysadmin area
- The Jira system details should be added to the configuration
- The configured external system must be loaded on the repository where the system will be used

If all the configuration items listed above is complete, you will be able to complete the steps below to link Symbio to Jira and start using the interface. 
See [Installation guide](installation_guide.md) for more details

## Linking a requirement domain to the Jira project
You must link a domain in the requirements facet to a Jira project for the integration to work. You can also link the Requirement domain to a project on Symbio.

Only connect **one** Jira Project to **one** domain! Connecting the same Jira project to multiple domains will cause unexpected behavior!
1. Go to the Requirements facet and create or select a domain
1. Select the Project from the list under the Jira Connection group on the details panel ![Jira Project Selection](media/connectJiraProject.png)

At this point, all of the requirements belonging to the domain with the "Send to Jira" attribute checked, and it's sub-domains will be synchronized with the Jira project. The synchronization will also sync all of the Issues(Requirements) in Jira to the selected domain.

## Creating requirements in Symbio and sending the requirement to Jira
1. The recommended way to create requirements is for you to create the requirement under the correct domain linked to the project first. This will ensure that the requirement is synchronized with the correct Jira project.
1. Check the "Send to Jira" check-box to trigger the synchronization of the new requirement to the Jira project. This happens in the background and no further action is required.
1. Activating the "Send to Jira" check-box, will make the requirement read-only. Changes are only allowed on Jira hence forth.

## Creating Jira Issues and sending them to Symbio
1. Creating an issue (requirement) on Jira will automatically send the requirement to the applicable domain in Symbio.

## Updating a requirement
1. Updating an issue on Jira will automatically update the requirement on Symbio