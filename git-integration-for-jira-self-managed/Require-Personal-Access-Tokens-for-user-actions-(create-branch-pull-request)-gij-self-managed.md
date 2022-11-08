---

title: Require Personal Access Tokens for user actions (create branch/pull request)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- how to -->

**What's on this page:**
- [Background](#background)
- [Objective](#objective)
  - [Supported integrations](#supported-integrations)
- [Instructions](#instructions)
- [What will Jira users see?](#what-will-jira-users-see)
- [Optional PAT setup for Create branches and Create pull request dialogs](#optional-pat-setup-for-create-branches-and-create-pull-request-dialogs)
- [More How-to articles](#more-how-to-articles)

<br>
<br>
<hr>
<br>
<br>

## Background

The Git Integration for Jira app allows users of integrations _(such as GitLab, GitHub and etc.)_ to create branches and pull requests from within the Jira issue. By default, the operation will be performed by the integration user that is used for indexing.

<img src='/wp-content/uploads/gij-jira-server-create-branch-example-01.png' width=680 height=506 alt='Jira issue page showing the Create Branch dialog where you can select a Repository, Base Branch and enter a user-defined Branch name. Create branch to proceed or Cancel to disregard.' style='display:block;margin:25px auto;max-width:100%'/>

<br>

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

<br>

## Instructions

To enable/disable the _**Require User PAT**_ setting for all repositories within an integration:

1.  Navigate to **Manage Git repositories**.

2.  Add a new integration or edit existing integration's feature settings.

    ![](/wp-content/uploads/gij-gitserver-webhook-cfg-edit-features-settings-sel-c.png)

    <br>

3.  Locate the **Require User PAT** setting.

    ![](/wp-content/uploads/gij-gitserver-edit-features-cfg-reqUserPAT-sel-c.png)

4.  Click the box to enable the requiring of user PAT.

5.  Click **Update** at the bottom of the page to save the setting.


## What will Jira users see?

1.  Once the Jira administrator requires Personal Access Tokens, your Jira users will be presented with a message that setup is required.

    ![](/wp-content/uploads/gij-gitserver-create-branch-dlg-start-c.png)

2.  Following that link, the PAT setup dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-setup-pat-dlg-c.png)
    
    *   Users will be prompted to enter their Personal Access Token (PAT) for the service (GitHub, GitLab, etc).
        
        **Instructions:** [Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

3.  With the Personal Access Token saved, the user will now see the following:

    ![](/wp-content/uploads/gij-gitserver-create-branch-dlg-use-pat-sel-c.png)

4.  Users can also go to the **Repository browser** screen and then configure the Personal Access Token for the repository via the ![](gij-edit-icon-dark.png) edit icon.

    ![](/wp-content/uploads/gij-gitserver-repo-browser-PAT-col-sel-c.png)

    *   The checkmark adjacent to the edit icon indicates that the PAT has been configured.

5.  Users can reconfigure the PAT in the Repository browser if it was changed from the git server or expired.

<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Personal Access Tokens are saved per integration by individual Jira users app. While the examples shown above are for the Create branch action, it is also applicable to the Create pull request action. The same token is used for Create branch and Create pull request functions.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Jira users must have the <b>View Development Tools</b> permission in the context of a Jira project to view content from the Git Integration for Jira app.
    </div>
    </div>
</div>
<br>

## Optional PAT setup for Create branches and Create pull request dialogs

Jira users can now provide their own PATS on the **Create branches** and **Create pull/merge request** dialogs even if it is not mandatory from the Jira admin.

<p>&nbsp;</p>

## More How-to articles

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Working with Custom API Path](/git-integration-for-jira-data-center/Working-with-Custom-API-Path-gij-self-managed)

[Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

**Require Personal Access Tokens for user actions (create branch/pull request)** (this page)

[Setting Project Permissions](/git-integration-for-jira-data-center/Setting-Project-Permissions-gij-self-managed)

[How to get a quote?](/git-integration-for-jira-data-center/How-to-get-a-quote-gij-self-managed)

[Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/Ways-to-Index-Git-Data-to-Jira-Issues-gij-self-managed)

[Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/Proxy-settings-on-adding-integrations-(except-AWS-CodeCommit)-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

