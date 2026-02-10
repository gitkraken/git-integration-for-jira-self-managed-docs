---

title: Enforce Git service permissions
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- General settings -->

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b><br>
        Available in Git Integration for Jira Server/Data Center <b>v4.1.4+</b>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This page is intended for Jira administrators. For Jira users with limited access, please <a href='/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed'>go to this page</a> instead.
    </div>
    </div>
</div>

<div class='embed-container embed-container--16-9'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/npe76i5nxm?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div style='text-align: center; margin-top: 10px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/npe76i5nxm'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

### Getting started

Source code is sensitive data and a great deal of effort is taken by development teams to get the permissions right. With the **Enforce Git service permissions** feature, your Git service permissions will be honored when presenting Jira users any Git data.

![](/wp-content/uploads/gij-serverdc-enforce-git-permissions-loc.png)

<div align=center>
    <i>Jira administrators can require individual Jira users to provide a Personal Access Token<br> from the related Git service to view Git Data.</i>
</div>
<br>

This setting provides Jira administrators the option of switching to a secure mode. In this mode, a Jira user is prevented from viewing git data, unless they have been authenticated to the Git server to view this specific data.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        A Jira user must have the <i><b>View development tools</b></i> Jira permission to be able to add a personal access token to an integration or repository.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This feature allows users to enter their PATs without accessing the Repository Browser page.
    </div>
    </div>
</div>

&nbsp;

### What Jira users will see when Git service permissions are enabled and they have not yet provided a Personal Access Token

![](/wp-content/uploads/gij-jira-issue-view-no-pat-and-enabled-secure-mode.png)

<div align=center>
    <i>When "Enforce Git service permissions" is enabled, Jira users with the "View development tools"<br> Jira permission will be prompted to provide a Personal Access Token <br>from the Jira user profile page.</i>
</div>

&nbsp;

### Jira user profile: Entering the Personal Access Token

From the Jira user profile page, the Jira user will enter their Git service Personal Access Token (PAT). For instructions on steps to create the appropriate token, see article [Creating Personal Access Tokens](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed).

![](/wp-content/uploads/gij-jira-user-profile-where-to-enter-pat.png)

<div align=center>
    <i>Connected integration are displayed in your user profile. Enter your personal access token<br> to gain access to git data (if permitted by your git service).</i>
</div>

&nbsp;

### Jira issue view: Git service permissions are enabled and a Jira user has provided a Personal Access Token

![](/wp-content/uploads/gij-jira-issue-view-pat-is-set-and-enabled-secure-mode.png)

<div align=center>
    <i>Git commits are displayed for users who entered a PAT and has git service <br>permission to view git data.</i>
</div>

&nbsp;

## Applied permissions

If the **Enforce Git service permissions** setting is enabled, a Jira user will see data only from the integrations for which their PAT has been provided. For example:

| Access location | Section | Condition(s) |
| :--- | :--- | :--- |
| Jira issue | Git Commits tab | Git data is only shown if the user has a Git server account, GitHub for example, that has permissions to this repository. |
| Jira issue | Git development panel | Users without permission can see the number of commits but won’t be able to view the commit code diffs, branch name or repository name. |
| Project sidebar | Git Commits | Git data is only shown if the user has a Git server account, GitHub for example, that has permissions to this repository. |
| Repository browser | Repository view | Git data is only shown if the user has provided a Git service account. |

&nbsp;

## Supported git platforms

| Integration | Supported? | Result |
| :--- | :--- | :--- |
| GitHub git repositories | Yes | **GITHUB CLOUD/SELF-HOSTED**<br>Users will only see the GitHub integration data when a PAT is provided for it. |
| GitLab git repositories | Yes | **GITLAB.COM/SELF-MANAGED GITLAB**<br>Users will only see the GitLab integration data when a PAT is provided for it. |
| Azure git repositories | Yes | **MICROSOFT AZURE DevOps/TFS/VSTS**<br>Users will only see the Azure/TFS/VSTS integration data when a PAT is provided for it. |
| AWS git repositories | No* | <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>COMING SOON</b><br>\*Support for AWS CC on the Enforce Git service permissions feature will be added sometime later in 2022. |

&nbsp;

## General setting: Enforce Git service permissions (advanced)

![](/wp-content/uploads/gij-enforce-git-service-permissions-advanced-general-setting.png)

**Max permission cache age** – This setting grants administrators the ability to set how long Git server permissions are cached in Git Integration for Jira app. The default value for this setting is **24** hours.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <a href='/git-integration-for-jira-data-center/require-user-pat-general-setting-gij-self-managed'>Require User PAT general setting</a> must be enabled to use the <b>Enforce Git Service permissions</b> feature.
    </div>
    </div>
</div>
<br>

