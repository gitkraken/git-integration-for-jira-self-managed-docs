---

title: Git Integration + Scriptrunner
description: 
taxonomy:
    category: git-integration-for-jira-data-center

---

<br>

ScriptRunner for Jira Server is an app available on the Atlassian Marketplace that allows you to extend Jira functionality 
through the use of built-in and custom groovy scripts.

<br>

It provides administrators with an in-line editor where you can write groovy scripts. Such script can be scheduled as 
a job or to be run on an issue transition withing Jira workflows or etc.
Out-of-the-box, you can find several built-in scripts ready to go, or you may try some recipes to start using a bit of 
groovy for custom scripts.

## API available

Which API or functions can be used in such scripts? Adaptavist lists [the next ones](https://scriptrunner.adaptavist.com/latest/jira/behaviours-api-quickref.html).
<br>

Git Integration for Jira provides additional Java API ([GIJFacade class](/git-integration-for-jira-data-center/javadocs-gijfacade-gij-self-managed/))
allowing you to operate with git information. 
The API is close to [Git integration for Jira REST API](/git-integration-for-jira-data-center/rest-api-gij-self-managed/) 
and provides similar functionality (and more):
*   Repositories - get list of repositories connected, create/delete/update a repository

*   Integrations - get list of integrations connected, create/delete/update an integration

*   Reindex - start a reindex of repository/integration, check whether the reindex is finished 

*   Commits - ...

*   CommitIssueChanges - ...

*   Branches - ...

*   Tags - ...

[GIJFacade](/git-integration-for-jira-data-center/javadocs-gijfacade-gij-self-managed/) is the main class having methods for all cases.
<br>
[JavaDocs](/git-integration-for-jira-data-center/javadocs-gij-self-managed/) for all classes used in GIJFacade see [nearby](/git-integration-for-jira-data-center/javadocs-gij-self-managed/).



## Examples of usage

**Example 1**: The API allows you to write a script re-associating git commits from one issue to another.
Without such script, you have to click each git commit and manually re-assign it to another issue to be shown 
on Git Commits issue tab of another issue.

**Example 2**: Create a pull request if an issue has been moved to CODE REVIEW status.
 
 **Example ...**: Here might be numerous examples that couldn't be possible without existence of GIJFacade class. 

## Tutorial

Further I'll demonstrate two things:
* getting started with Scriptrunner plugin
* a creation of a simple script retrieving list of commits associated with issue "TST-1"
* a setup of issue workflow in a such way that if an OPEN issue has at least one git commit then it's moved to IN PROGRESS status

## Getting started with Scriptrunner plugin

* Install Scriptrunner plugin. As a result the next pages are available in administration.
* None GIJ configuration is required


### How to run a simple script

Precondition:
* GIJ plugin is installed.
* Some repository is connect.
* You have an issue (e.g. TST-1) having git commits associated with it on Git Commits issue tab.

Steps
* open Scriptrunner console
* input the next code
* press "Run" button
* a result of the last operation is displayed at the bottom. In our case it's a list of commits associated with issue "TST-1".
Please be aware, that objects are logged using the shortest information by default. If you'd like to   
* pay your attention to "Logs" tab at the bottom
* please be aware, that 

## Permissions

Permissions model is provided by Scriptrunner. So read its documentation.


## Old stuff below. todo: delete

On Jira Cloud, the Automation for Jira has been completely integrated into Jira Cloud and no longer exists as a standalone app in the Atlassian Marketplace. For Jira Server/Data Center, you will need to download and install Automation for Jira - Data Center and Server from the Atlassian Marketplace.

### Downloading the app

1.  Go to [Automation for Jira - Data Center and Server](https://marketplace.atlassian.com/apps/1215460/automation-for-jira-data-center-and-server?hosting=datacenter&tab=overview) and start the free trial or buy it now.

2.  Login to your Atlassian account when prompted and generate a new license for the trial.

3.  IMPORTANT Make sure to copy your license and save it.

4.  Click **Download** to download the app to your local system.


### Installing the app

<b style='color: #63B9CC'>REQUIRES ADMIN ACCESS</b>

1.  On your Jira Server/Data Center instance, navigate to Manage apps (Jira settings ➜ Apps ➜ **Manage apps**).

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/jira-admin-cfg-manage-apps-upload-app-sel(c).png?api=v2)

2.  Click **Upload app** and locate the downloaded A4J JAR file.

3.  After the installation, look under the User-installed apps and open the **Automation for Jira** tab.

4.  Paste the license key into the provided box then click **Update**.


## General settings for A4J

<b style='color: #63B9CC'>ADMINS</b>

Before you can use the full extent of this feature, make sure that it is enabled in the Git Integration for Jira app General settings.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/jira-server-gen-cfg-jira-automation-setting.png?api=v2)

## How to set up automation templates

Create a rule to configure triggers and actions for automating tasks. There are two levels:

### Project level (projects)

Project rules only apply within specific projects.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/gitserver-proj-settings-automation-sel-a1.png?api=v2)

1.  Open a project to work on, then go to ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/1390985508/6452/54e101d7235b2d7307c412fdfb4c3bd12f35dd91/_/images/icons/emoticons/72/2699.png) **Project settings**.

2.  On the sidebar, click **Project automation**.

3.  On the Automation screen, click **Project rules.**

    *   OPTIONAL Click **Add template rules** to add built-in preset automation rules generated by Git Integration for Jira app to the current project.

4.  Click **Create rule** (adjacent to **...**) to manually create a new automation rule for the current project. Skip the tour, if prompted, then proceed to start creating the new rule.

5.  Configure triggers, conditions and actions for this rule.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/gitserver-create-automation-rule-example(c1).png?api=v2)

6.  For the above example:

    *   **TRIGGER** – This rule will trigger when a pull request is created.

    *   **CONDITION** – When the status of the Jira issue is IN PROGRESS, it will perform the actions below.

    *   **ACTIONS** – If the condition(s) are met, the rule will fire up the action(s) -- assigns the issue to a specific group REVIEWERS and transitions the Jira issue to IN REVIEW.

7.  Enter a descriptive name for this rule in the provided box.

8.  Click **Turn it on** to publish and activate it. The new rule is added to the automation list.


![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/gitserver-create-automation-rule-list-sel.png?api=v2)

### Global administration level (system)

Global rules apply to all projects. If there are similar automation rule triggers from one or more projects, the global rule is executed first.

The steps for creating automation rules for global level is exactly the same as the Project level instructions.

1.  Access the global automation rules via Jira settings ➜ **System**.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/gitserver-system-menu-sidebar-automation(c).png?api=v2)

2.  On the sidebar under Automation for Jira, click **Automation rules**.

3.  Click **Create rules**.

4.  Configure triggers, conditions and actions for this rule.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/gitserver-global-automation-rule-example-2(c1).png?api=v2)

    *   **TRIGGER** – This rule will trigger when a commit is created.

    *   **CONDITION** – When the ASSIGNEE is the commit author, it will perform the action(s) below.

    *   **ACTIONS** – If the condition(s) are met, the rule will fire up the actions – assign the issue to a specific group TESTERS and transitions the Jira issue to IN TESTING.

5.  Enter a descriptive name for this rule in the provided box.

6.  Click **Turn it on** to publish and activate it. The new rule is added to the automation list.


![](https://bigbrassband.atlassian.net/wiki/download/attachments/2126905349/gitserver-global-automation-rule-list-add.png?api=v2)

## Known issue

![(info)](https://bigbrassband.atlassian.net/wiki/s/1390985508/6452/54e101d7235b2d7307c412fdfb4c3bd12f35dd91/_/images/icons/emoticons/information.png) The limitation of Git Integration for Jira (GIJ) app not working with Automation for Jira (A4J) Lite is not a GIJ limitation but an Atlassian limitation.

## Advanced Examples

For advanced examples, see sub-page [Automation Advanced Examples](https://bigbrassband.atlassian.net/wiki/spaces/GITCLOUD/pages/1714257921).

## More related topics about Jira automation

*   [A4J advanced examples](/git-integration-for-jira-data-center/Git-integration-plus-Jira-automation-advanced-examples-gij-self-managed/)

*   [A4J library templates](/git-integration-for-jira-data-center/Git-Integration-for-Jira-automation-template-library/)

