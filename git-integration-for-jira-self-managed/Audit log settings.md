---

title: Audit log settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Audit log settings

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1207828866/Audit+log+settings>

* * *

VERSION 3.8 NEW FEATURE

This setting is part of the [**General Settings**](/wiki/spaces/GIJDC/pages/966852655/General+Settings) configuration page.

  
These settings affect which audit logs are displayed on the Jira system administration audit log page.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207828866/gitserver-gencfg-audit-log.png?version=1&modificationDate=1647771827039&cacheVersion=1&api=v2&width=557&height=108)

With auditing feature, key activities are tracked on the Jira instance. This provides administrators insight on how the way the instance is being used.

The new audit log will help administrators:

*   manage their log more effectively;
    
*   decide which of the coverage areas to audit; and
    
*   select how detailed they want their log to be.
    

The audit log functionality is also extended to Jira Data Center instances as it will have more coverage areas, various event volume levels and an option to integrate the audit log file with external tools.

For more information on the audit log and it’s new functions, see [**this article**](https://confluence.atlassian.com/jiracore/audit-log-improvements-989762528.html).

**Performance**  
Using this feature affects database performance. Administrators can select only needed log events to audit to improve performance.

## Enable audit logging

This setting enables/disables audit logging for the Git Integration for Jira app. This setting is set to ON for new app installations and is set to OFF on app upgrades by default.

## Audit log events

Click **Advanced** to expand the audit log events. Enable/disable event items to turn tracking ON/OFF for specific events.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828866/jira-server-gencfg-audit-log-advanced.png?version=1&modificationDate=1613126222038&cacheVersion=1&api=v2)

## View Jira audit log

Click this label link to take you to the Jira administrator system Audit log page. Alternatively, go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Jira administration** ➜ **System** ➜ **Audit log**.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828866/jira-server-audit-log-navigation.png?version=1&modificationDate=1613126221574&cacheVersion=1&api=v2)

Below is an example of the logs audited of the selected events from the **Audit logs - General settings**:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828866/jira-audit-log-example.png?version=1&modificationDate=1613126221815&cacheVersion=1&api=v2)

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