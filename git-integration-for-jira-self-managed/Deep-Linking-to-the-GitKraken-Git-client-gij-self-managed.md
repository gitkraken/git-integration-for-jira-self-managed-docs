---

title: Deep Linking to the GitKraken Git client
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b>
<br>

<img src='https://www.gitkraken.com/wp-content/uploads/2023/01/Group-812.svg' style='margin:30px auto 35px auto;' />

[GitKraken Git Client](https://www.gitkraken.com/git-client/features) is a multi-platform application which allows integration of Git repositories such as GitHub, GitLab, Bitbucket, Azure DevOps, Jira, and more. It provides a seamless approach to visualize Git, helping thousands of developers save time with their development workflow. It grants flexibility with switching between a GUI or a terminal. It also possesses robust team features which affords a seamless experience with Git -- whether you work on Windows, Mac or Linux.

## Video guide

<div class='embed-container' style='padding-bottom: 67.08%'>
    <iframe width='709' height='476' src='https://fast.wistia.com/embed/iframe/n3ctymt8tq?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div style='text-align: center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/n3ctymt8tq'><b>here</b></a> to open this video in a new tab/window for more viewing options</i>.
</div>
<br>

## Deep link access locations

![](/wp-content/uploads/gij-gitserver-gk-deeplinking-01c.png)

The GitKraken deep links are accessible on the following locations:

### Jira issue – Git commits tab

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-issue-git-commits.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Commits panel in the Git Commits tab' />

### Jira issue Git developer panel – branches and tags lists

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-issue-branches.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Branches list on the Jira issue Git development panel' />

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-issue-tags.png' style='margin:0 auto 25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Tags list on the Jira issue Git development panel' />

### Repository browser – All repository table

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-repo-browser-actions.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Repository browser -- Repositories list' />

### Repository browser – Browse page (latest commit)

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-repo-browser-latest-commit.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Repository browser (Browse page)-- latest commit label link' />

### Repository browser – Commits page

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-repo-browser-commit.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Repository browser -- Commits page' />

### Repository browser – Compare page (commit view)

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-repo-browser-compare.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitKraken in the Repository browser -- Compare page' />

### Repository browser - Browse tab -- Open into GitKraken deeplink

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-repo-browser-open-link.png'  style='margin:25px auto;display:block;' alt='Access the Open into GitKraken button on the Repository browser -- Browse tab' />

### Repository browser - Commits tab -- Open into GitKraken deeplink

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-repo-browser-open-link-commits.png'  style='margin:25px auto;display:block;' alt='Access the Open into GitKraken button in the Repository browser -- Commits tab' />

### Repository browser - Tags -- Open into GitKraken deeplink

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-open-button-repo-browser-tags.png'  style='margin:25px auto;display:block;' alt='Access the Open into GitKraken button in the Repositry browser -- Tags dropdown' />

### Jira issue Git Commits tab deeplinking panel

Use the deeplinking panel on the Jira issue Git Commits tab to download the GitKraken Git client.

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-open-button-git-commits-issue-tab.png' style='margin:25px auto;display:block;' alt='Use the deeplinking panel on the Jira issue Git Commits tab to download the GitKraken Git client app' />

### Jira issue Git development sidebar deeplinking panel

Use the deeplinking panel on the Jira issue Git development sidebar to download the GitKraken Git client.

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-open-button-dev-panel.png' style='margin:25px auto;display:block;' alt='Use the deeplinking panel on the Jira issue Git development sidebar to download the GitKraken Git client app' />

## Profile settings

Individual Jira Data Center users can enable or disable the GitKraken integration with Git Integration for Jira Data Center by visiting the **Git Integration: User settings** page.

1.  From the Jira menu, go your **Jira Profile**. The Summary page is displayed.

2.  Scroll down to _**Git Integration for Jira preferences**_ section.

    ![](/wp-content/uploads/gij-gitserver-gitlens-deeplinking-profile-cfg.png)

3.  Click the edit icon. The following dialog is displayed.

4.  Enable/disable the GitKraken integration using the dropdown. Default setting is `Enabled`.

    ![](/wp-content/uploads/gij-gitserver-gitkraken-deeplinking-profile-prefs-gitkraken.png)

5.  Click **Update** to save the settings.

<br>

## Administrator settings

Jira Data Center administrators can disable or enable the GitKraken integration with Git Integration for Jira Data Center for all Jira users. All Jira Server users can enable the GitKraken integration separately (see [Profile settings](#Profile-settings)).

Go to the Git Integration for Jira – **General settings** tab (sidebar).

Enable/disable this setting under **GitKraken integration** section.

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitkraken-general-settings.png'  style='margin:25px auto;display:block;' alt='Access the GitKraken integration option to enable/disable the feature in the General settings of the Git Integration for Jira app' />

<br>

<b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px 5px 0; font-size: small;'>GIT INTEGRATION: JIRA CLOUD</b> <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px 5px 0; font-size: small;'>COMING SOON</b>

User settings is added to support non-admin users to be able to enable/disable this feature.

<p>&nbsp;</p>

## See more Git Integration for Jira app features

[Indexing queue viewer](/git-integration-for-jira-data-center/Indexing-queue-viewer-gij-self-managed) (Git Integration for Jira Server/Data Center)

**Deep Linking to the GitKraken Git client** (this page)

[Deep Linking into GitLens](/git-integration-for-jira-data-center/Deep-Linking-into-GitLens-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Git Integration + Jira Automation (Jira Server \| DC)](/git-integration-for-jira-data-center/Git-integration-plus-Jira-automation-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating branches](/git-integration-for-jira-data-center/Creating-branches-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/Creating-pull-merge-requests-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/Associate-Pull-Merge-Requests-to-Issues-Based-on-Commits-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Issue Git integration panel](/git-integration-for-jira-data-center/Issue-Git-integration-panel-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/Smart-commits-overview-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/Shared-reindex-queue-between-DC-nodes-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Enforced git permissions for Jira users](/git-integration-for-jira-data-center/Enforced-git-permissions-for-Jira-users-gij-self-managed) (Git Integration for Jira Server/Data Center)

