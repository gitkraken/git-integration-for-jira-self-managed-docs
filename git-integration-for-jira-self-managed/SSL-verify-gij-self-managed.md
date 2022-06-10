---

title: SSL verify
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This feature can be accessed at the following locations on the Manage Git repositories page:

*   **EXISTING INTEGRATION** <br>Actions ➜ **Edit integration connection settings**

*   **EXISTING REPOSITORY** <br>Actions ➜ **Edit repositories settings** ➜ Repository Settings section

*   **NEW REPOSITORY** <br>Connect to Git repository ➜ **Advanced setup** ➜ Repository Settings section

*   **EXISTING INTEGRATION \| EXISTING REPOSITORY** <br>Under **Repository/integration** _column_ ➜ click an integration or repository URL name

* * *

The **SSL Verify** option is set to `Enabled` by default. If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397639/gitserver-integration-repo-settings-SSLv-sel.png?version=1&modificationDate=1630642850012&cacheVersion=1&api=v2&width=680&height=508)

<div align='center'><i>In the above example, the Integration Connection Settings screen from Git Integration for Jira Server/Data Center is shown.</i></div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <b>SSL Verify</b> setting is available in Jira Server, Data Center and Jira Cloud. This option is not available for non-fetched repositories.
    </div>
    </div>
</div>

