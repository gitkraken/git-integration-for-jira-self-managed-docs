---

title: Enforced git permissions for Jira users - Features
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- features -->

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Available in Git Integration for Jira Data Center/Server <b>v4.1.4+</b>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This page is intended for Jira users with limited access. If you are a Jira administrator, please <a href='/git-integration-for-jira-data-center/enforce-git-service-permissions-gij-self-managed'>go to this page</a> instead.
    </div>
    </div>
</div>
<br>

Source code is sensitive data and development teams take a great deal of effort to get the permissions right. When the **Enforce Git service permissions** setting is enabled by your administrator, the Git service permissions will be honored when presenting any Git data to Jira users.

This state is called secure mode – where a Jira user is limited from viewing git data, unless they have been authenticated to the Git server to view this specific data.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Requirements</b><br>
        When "Enforce Git service permissions" is enabled, Jira users with the <i><b>View development tools</b></i> Jira permission will be prompted to provide a <b>Personal Access Token</b> in the Jira user profile page.
    </div>
    </div>
</div>
<br>


## What a Jira user will see while in this mode and has not yet provided a Personal Access Token:

![](/wp-content/uploads/gij-gitserver-secure-mode-users-01.png)

<div style='text-align:center;font-style:italic;margin-top:10px'>
    Click the <img src='/wp-content/uploads/gij-key-icon.png' style='margin:0 3px' /> icon in the Git Commits tab or the **Set up** label under Git Integration panel and <br>
enter your personal access token to view git data (if permitted via your Git service).
</div>

<br>

## Jira user profile: Entering the Personal Access Token

From the Jira user profile page, the Jira user can enter their Git service Personal Access Token (PAT). For instructions on creating the appropriate token, see article [Creating Personal Access Tokens](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed).

![](/wp-content/uploads/gij-gitserver-secure-mode-users-02.png)

<div style='text-align:center;font-style:italic;margin-top:10px'>
    Connected integration are displayed in your user profile. Enter your personal <br>
access token to gain access to git data (if permitted by your git service).
</div>

<br>

## Jira issue view: Git service permissions setting is enabled and a Jira user has provided a Personal Access Token

![](/wp-content/uploads/gij-gitserver-secure-mode-users-01.png)

<div style='text-align:center;font-style:italic;margin-top:10px'>
    Git commits are displayed for users who entered a PAT and has <br>git service permission to view git data.
</div>

<br>

<p>&nbsp;</p>

## See more Git Integration for Jira app features

[Indexing queue viewer](/git-integration-for-jira-data-center/Indexing-queue-viewer-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking to the GitKraken Git client](/git-integration-for-jira-data-center/Deep-Linking-to-the-GitKraken-Git-client-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking into GitLens](/git-integration-for-jira-data-center/Deep-Linking-into-GitLens-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Git Integration + Jira Automation (Jira Server \| DC)](/git-integration-for-jira-data-center/Git-integration-plus-Jira-automation-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating branches](/git-integration-for-jira-data-center/Creating-branches-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/Creating-pull-merge-requests-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/Associate-Pull-Merge-Requests-to-Issues-Based-on-Commits-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Issue Git integration panel](/git-integration-for-jira-data-center/Issue-Git-integration-panel-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/Smart-commits-overview-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/Shared-reindex-queue-between-DC-nodes-gij-self-managed) (Git Integration for Jira Server/Data Center)

**Enforced git permissions for Jira users** (this page)

