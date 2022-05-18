---

title: Require User PAT general setting
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
For detailed information on this feature, see [Documentation: Require user personal access tokens for branch and PR/MR creation](/wiki/spaces/GIJDC/pages/317390849).

VERSION 3.8.1 Git Integration for Jira adds three new settings in the General settings configuration page:

*   Repository Browser

*   Source Code Diff Viewing

*   Require user personal access tokens for branch and PR/MR creation (this page)


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1947107395/gitserver-gencfg-req-pat-tokens.png?version=1&modificationDate=1647773429777&cacheVersion=1&api=v2&width=680&height=120)

When enabled, this setting requires Jira users to configure personal access tokens to allow them to create branches or pull requests from Jira.

|     |     |
| --- | --- |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1947107395/gitserver-create-pullreq-dlg-reqPAT.png?version=1&modificationDate=1631802924891&cacheVersion=1&api=v2) | ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1947107395/gitserver-create-branch-req-user-pat-enabled-aws.png?version=1&modificationDate=1631802924630&cacheVersion=1&api=v2) |


The default setting is `Disabled` for new and existing Git Integration for Jira app installations. This setting is retained on restore/upgrade of the app.

If this setting is enabled (_checked_) in General settings, the users are required to setup personal access tokens for the connected repository and to be able to create branches and PR/MR from Jira. This general setting will override the repository and integration settings, regardless if they were set to `OFF`.

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