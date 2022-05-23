---

title: Connecting to a git host account via Add new integration panel
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This process requires a git host account (e.g. GitHub/GitLab/VSTS etc.) Use the Add new integration panel in Jira Cloud/Server to connect git repositories from git hosts to Jira. This is the recommended way of integrating your multiple git repositories to Jira.

1. On your Jira dashboard menu, click Git ➜ **Manage repositories**.

2\. Click a git host on the Add new integration panel.

Select from the supported git host integration (_or click the integration links below to follow to their own integration guide_):

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-github-icon.png?version=1&modificationDate=1640772744579&cacheVersion=1&api=v2)](/wiki/spaces/GIJDC/pages/91979804/GitHub.com)

[GitHub.com](/wiki/spaces/GIJDC/pages/91979804/GitHub.com)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-github-ent-icon.png?version=1&modificationDate=1640772744866&cacheVersion=1&api=v2)](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server)

[GitHub Enterprise Server](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-bitbucket-icon.png?version=1&modificationDate=1640772745139&cacheVersion=1&api=v2)](/git-integration-for-jira-self-managed/Bitbucket-Server)

[Bitbucket](/git-integration-for-jira-self-managed/Bitbucket-Server)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-gitlab-icon.png?version=1&modificationDate=1640772745416&cacheVersion=1&api=v2)](/wiki/spaces/GIJDC/pages/91881531/GitLab.com)

[GitLab.com](/wiki/spaces/GIJDC/pages/91881531/GitLab.com)

[![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2044035170/gitcloud-gitlab-ceee-icon.png?version=1&modificationDate=1640772745685&cacheVersion=1&api=v2&width=48&height=48)](/wiki/spaces/GIJDC/pages/91947056)

[GitLab CE/EE](/wiki/spaces/GIJDC/pages/91947056)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-awscc-icon.png?version=1&modificationDate=1640772745948&cacheVersion=1&api=v2)](/git-integration-for-jira-self-managed/AWS-CodeCommit)

[AWS CodeCommit](/git-integration-for-jira-self-managed/AWS-CodeCommit)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-microsoft-icon.png?version=1&modificationDate=1640772746210&cacheVersion=1&api=v2)](/wiki/spaces/GIJDC/pages/92176406)

[Azure DevOps / VSTS](/wiki/spaces/GIJDC/pages/92176406)

[![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2044035170/gitcloud-autoconnect-azure-tfs-icon.png?version=1&modificationDate=1640772746486&cacheVersion=1&api=v2&width=48&height=48)](/wiki/spaces/GIJDC/pages/91979843)

[Azure DevOps Server / TFS](/wiki/spaces/GIJDC/pages/91979843)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-gerrit-icon.png?version=1&modificationDate=1640772746746&cacheVersion=1&api=v2)](/git-integration-for-jira-self-managed/Gerrit)

[Gerrit](/git-integration-for-jira-self-managed/Gerrit)

[![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/gitcloud-git-icon.png?version=1&modificationDate=1640772747020&cacheVersion=1&api=v2)](/wiki/pages/resumedraft.action?draftId=92078126)

[Git](/wiki/spaces/GIJDC/pages/2044035207)

3\. The Connect Wizard is displayed.  Enter login credentials. If two-factor authentication is enabled for your git host, enter the token as the password instead. Follow screen instructions to import git repositories.

4\. On the following screen, change settings as required or leave the default settings as is.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035170/git-server-dc-new-settings-auto-connect-wiz.png?version=1&modificationDate=1640772747294&cacheVersion=1&api=v2)

*   On the Integration Settings, setting the [**Require User PAT** option](/wiki/spaces/GIJDC/pages/317390849) to `ON` will require users to provide PAT which will be used for branch and merge/pull request creation/deletion (via the developer panel on the Jira issue page). This is a security feature of Git Integration for Jira app for git hosts that support two-factor authentication. This option requires the **[Repository Browser](/wiki/spaces/GIJDC/pages/1930398739)** feature to be enabled.




Do not enable this feature for connected git hosts that don't support it. For example, TFS2013/2015 does not support PATs. Users won't be able to create branches or create pull/merge request if the above setting is **`ON`**.

*   Jira administrators can configure the **Require User PAT** setting when connecting a 2FA git host via the Add new integration panel or via **Edit integration settings** in the **Manage repositories page**. If set to **`ON`**, Jira Users are required to set their PAT for specific repositories via Repository Browser. The setup PAT link is accessible via the developer panel on Create Branch or Create Pull/Merge Request dialogs in the Jira issue page.



This setting is only available for **auto-connected** git hosts configured via Add new integration wizard with Git Integration for Jira app.

*   For more information on Project permissions and repository associations, see **[Setting Project Permissions](/wiki/spaces/GIJDC/pages/1930397766/Associating+project+permissions)**.

5. Click **Finish** to accept the settings and complete the setup.



