---

title: Email settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Email settings

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1207795941/Email+settings>

* * *

This setting is part of the [**General Settings**](/wiki/spaces/GIJDC/pages/966852655/General+Settings) configuration page.

  
The settings in this group controls email notifications and recipient filters.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795941/gitserver-gencfg-email-settings.png?version=1&modificationDate=1647774129291&cacheVersion=1&api=v2&width=678&height=181)

## Send commit notification emails

Enable/disable the setting to allow sending of email notifications when a commit is made.  This setting defaults to OFF for our app upgrades and ON for new installations of the Git Integration for Jira app.  This setting also enables/disables email notifications related to smart commits.

In the provided box, enter a regular expression to send e-mail only to addresses that matches this pattern.  Leave this field blank to disable this filter.

No notifications are sent when this setting is off, if the provided regex box is blank, or regular expression doesn't have a match.

For more information, see [**Commit Email Notifications**](https://www.bigbrassband.com/git-integration-for-jira/documentation/commit-email-notifications.html).

To avoid the possibility to set invalid regular expressions in the provided regex box, the **To address** must match the regex pattern.

Disabling this setting will improve Jira performance.

* * *

### More on general settings

*   Page:
    
    [Git roll up issue tab](/wiki/spaces/GIJDC/pages/1207828678/Git+roll+up+issue+tab) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git commits issue and project tabs](/wiki/spaces/GIJDC/pages/1207828697/Git+commits+issue+and+project+tabs) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git integration features](/wiki/spaces/GIJDC/pages/1207795905/Git+integration+features) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Branch and pull request settings (formerly Git Integration Options)](/wiki/spaces/GIJDC/pages/1207828745) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Email settings](/wiki/spaces/GIJDC/pages/1207795941/Email+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Scheduled jobs](/wiki/spaces/GIJDC/pages/1207795958/Scheduled+jobs) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Audit log settings](/wiki/spaces/GIJDC/pages/1207828866/Audit+log+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [General settings](/wiki/spaces/GIJDC/pages/1930398111/General+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Repository Browser general setting](/wiki/spaces/GIJDC/pages/1947140158/Repository+Browser+general+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Source Code Diff Viewing general setting](/wiki/spaces/GIJDC/pages/1947140173/Source+Code+Diff+Viewing+general+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Require User PAT general setting](/wiki/spaces/GIJDC/pages/1947107395/Require+User+PAT+general+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Enable Automation for Jira general setting](/wiki/spaces/GIJDC/pages/2045149338/Enable+Automation+for+Jira+general+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Enforce Git service permissions](/wiki/spaces/GIJDC/pages/2091810842/Enforce+Git+service+permissions) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Per Node Repository Indexing](/wiki/spaces/GIJDC/pages/2095775749/Per+Node+Repository+Indexing) (Git Integration for Jira Data Center)