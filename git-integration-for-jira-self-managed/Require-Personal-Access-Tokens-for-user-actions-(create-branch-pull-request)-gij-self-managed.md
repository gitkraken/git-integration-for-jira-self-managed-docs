---

title: Require Personal Access Tokens for user actions (create branch/pull request)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## Background

The Git Integration for Jira app allows users of integrations _(such as GitLab, GitHub and etc.)_ to create branches and pull requests from within the Jira issue. By default, the operation will be performed by the integration user that is used for indexing.

![Jira issue page showing the Create Branch dialog where you can select a Repository, Base Branch and enter a user-defined Branch name. Create branch to proceed to Cancel to disregard.](https://bigbrassband.atlassian.net/wiki/download/thumbnails/317390849/jira-server-create-branch-example-01.png?version=3&modificationDate=1641640872850&cacheVersion=1&api=v2&width=680&height=506)

## Objective

For teams looking to maintain user attribution, Jira administrators can require that individual Jira users provide personal access tokens to perform actions such as creating a branch or pull request in Jira. This can be done by using their git service account rather than the integration account.

### Supported integrations

User attribution is supported in the following special integrations in Git Integration for Jira Server:

*   GitHub.com

*   GitHub Enterprise

*   GitLab.com

*   GitLab self-managed

*   Microsoft Azure DevOps

*   Microsoft Visual Studio Team Services (VSTS)

*   Microsoft Team Foundation Server (TFS)

*   AWS CodeCommit


## Instructions

To enable/disable the _**Require User PAT**_ setting for all repositories within an integration:

1.  Navigate to **Manage Git repositories**.

2.  Add a new integration or edit existing integration's feature settings.

3.  ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/317390849/gitserver-webhook-cfg-edit-features-settings-sel(c).png?version=1&modificationDate=1641640872899&cacheVersion=1&api=v2&width=646&height=438)

    Locate the **Require User PAT** setting.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/317390849/gitserver-edit-features-cfg-reqUserPAT-sel(c).png?version=1&modificationDate=1641640872903&cacheVersion=1&api=v2&width=646&height=543)
4.  Click the box to enable the requiring of user PAT.

5.  Click **Update** at the bottom of the page to save the setting.


## What will Jira users see?

1.  Once the Jira administrator requires Personal Access Tokens, your Jira users will be presented with a message that setup is required.

2.  ![](https://bigbrassband.atlassian.net/wiki/download/attachments/317390849/gitserver-create-branch-dlg-start(c).png?version=1&modificationDate=1641641133909&cacheVersion=1&api=v2)

    Following that link, the PAT setup dialog is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/317390849/gitserver-setup-pat-dlg(c).png?version=1&modificationDate=1641640873034&cacheVersion=1&api=v2)
    *   Users will be prompted to enter their Personal Access Token (PAT) for the service (GitHub, GitLab, etc).
        Instructions: Creating Personal Access Tokens

3.  With the Personal Access Token saved, the user will now see the following:

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/317390849/gitserver-create-branch-dlg-use-pat-sel(c).png?version=1&modificationDate=1641640873038&cacheVersion=1&api=v2)
4.  Users can also go to the **Repository browser** screen and then configure the Personal Access Token for the repository via the ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) edit icon.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/317390849/gitserver-repo-browser-PAT-col-sel(c).png?version=1&modificationDate=1641640873041&cacheVersion=1&api=v2)
    *   The checkmark adjacent to the edit icon indicates that the PAT has been configured.

5.  Users can reconfigure the PAT in the Repository browser if it was changed from the git server or expired.


Personal Access Tokens are saved per integration by individual Jira users app. While the examples shown above are for the Create branch action, it is also applicable to the Create pull request action. The same token is used for Create branch and Create pull request functions.

Jira users must have the **View Development Tools** permission in the context of a Jira project to view content from the Git Integration for Jira app.

## Optional PAT setup for Create branches and Create pull request dialogs

Jira users can now provide their own PATS on the **Create branches** and **Create pull/merge request** dialogs even if it is not mandatory from the Jira admin.