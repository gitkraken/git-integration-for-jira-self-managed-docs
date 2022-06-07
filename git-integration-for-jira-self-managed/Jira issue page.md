---

title: Jira issue page
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
If the Git Integration for Jira app is configured and licensed successfully, new tabs are added to each Jira issue.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Some features can be switched on and off via <a href='/git-integration-for-jira-self-managed/general-settings-docs/'>General settings</a>:
        <ul>
            <li>Jira dashboard menu Git ➜ Manage repositories ➜ <i>Git Integration for Jira (sidebar)</i> ➜ <b>General settings</b>.</li>
        </ul>
    </div>
    </div>
</div>
<br>

Also, users should be able to see available features in the Jira issue page.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930398870/gitserver-jira-issue-page-sample.png?version=1&modificationDate=1630642910535&cacheVersion=1&api=v2)

<br>

| **Label** | **Description** |
| --- | --- |
| **1** | **Git Roll Up** <br>In this tab, service users will be able to see commit statistics, <br>In this tab, service users will be able to see commit information such as commit author, changes to source files, as well as viewing the full commit that are associated to the current issue. |
| **3** | **Jira Development Panel** <br>The Jira Development Panel is located on the right panel of the Jira issue page under **Git integration** section. In most cases, this panel is intended for developers. |
| **4** | **Compare Code** <br>Click the label link to open the Compare Code dialog and allows service users to do a branch-to-branch or branch-to-master code comparison from a specific repository. |
| **5** | **Branches** <br>This feature allows service users to create git branches against the specified repository from inside Jira. The created branches are also displayed as a list. |
| **6** | **Ahead and Behind** <br>Represents the number of commits that are ahead/behind the main branch. |
| **7** | **Pull/Merge Request** <br>This feature allows service users to create pull/merge request against the specified repository from inside Jira. The created pull/merge requests are also displayed as a list. |
| **8** | **Tags** <br>Git tags are read from the associated repository and are displayed as a list. |

