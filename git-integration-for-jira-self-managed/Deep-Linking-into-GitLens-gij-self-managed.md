---

title: Deep Linking to GitLens
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b>
<br>

<img src='https://www.gitkraken.com/wp-content/uploads/2023/01/Group-17491.svg' style='margin:30px auto 35px auto;' />

[GitLens](https://www.gitkraken.com/gitlens) is a Visual Studio Code extension and supercharges GIt inside VS Code while helping users visualize code, explore Git repositories, use powerful compare commands and so much more.

Support for GitLens deep linking is now available in Git Integration for Jira app. Open repositories, commits, tags, and branches into GitLens using the relevant access locations in Jira.

&nbsp;

### Deep link access locations

The GitLens deep links are accessible on the following locations:

#### Jira issue – Git commits tab

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-issue-git-commits.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitLens in the Commits panel in the Git Commits tab' />

#### Jira issue Git developer panel – branches and tags lists

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-issue-branches.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitLens in the Branches list on the Jira issue Git development panel' />

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-issue-tags.png' style='margin:0 auto 25px auto;display:block;' alt='Shows the deeplink for GitLens in the Tags list on the Jira issue Git development panel' />

#### Repository browser – All repository table

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-repo-browser-actions.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitLens in the Repository browser -- Repositories list' />

#### Repository browser – Browse page (latest commit)

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-repo-browser-latest-commit.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitLens in the Repository browser (Browse page)-- latest commit label link' />

#### Repository browser – Commits page

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-repo-browser-commit.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitLens in the Repository browser -- Commits page' />

#### Repository browser – Compare page (commit view)

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-repo-browser-compare.png' style='margin:25px auto;display:block;' alt='Shows the deeplink for GitLens in the Repository browser -- Compare page' />

#### Repository browser - Browse tab -- Open into GitLens deeplink

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-repo-browser-open-link.png'  style='margin:25px auto;display:block;' alt='Access the Open into GitLens button on the Repository browser -- Browse tab' />

#### Repository browser - Commits tab -- Open into GitLens deeplink

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-repo-browser-open-link-commits.png'  style='margin:25px auto;display:block;' alt='Access the Open into GitLens button in the Repository browser -- Commits tab' />

#### Repository browser - Tags -- Open into GitLens deeplink

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-open-button-repo-browser-tags.png'  style='margin:25px auto;display:block;' alt='Access the Open into GitLens button in the Repositry browser -- Tags dropdown' />

#### Jira issue Git Commits tab deeplinking panel

Use the deeplinking panel on the Jira issue Git Commits tab to download the GitLens extension.

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-open-button-git-commits-issue-tab.png' style='margin:25px auto;display:block;' alt='Use the deeplinking panel on the Jira issue Git Commits tab to download the GitLens extension' />

#### Jira issue Git development sidebar deeplinking panel

Use the deeplinking panel on the Jira issue Git development sidebar to download the GitLens extension.

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-open-button-dev-panel.png' style='margin:25px auto;display:block;' alt='Use the deeplinking panel on the Jira issue Git development sidebar to download the GitLens extension' />

&nbsp;

### Profile settings

Individual Jira Data Center users can enable or disable the GitLens integration with Git Integration for Jira Data Center by visiting the Git Integration: User settings page.

1.  From the Jira menu, go your **Jira Profile**. The Summary page is displayed.

2.  Scroll down to _**Git Integration for Jira preferences**_ section.

    ![](/wp-content/uploads/gij-gitserver-gitlens-deeplinking-profile-cfg.png)

3.  Click the edit icon. The following dialog is displayed.

4.  Enable/disable the GitLens integration using the dropdown. Default setting is `Enabled`.

    ![](/wp-content/uploads/gij-gitserver-gitlens-deeplinking-profile-prefs-gitlens.png)

5.  Click **Update** to save the settings.

&nbsp;

### Administrator settings

The GitLens deeplinking feature is enabled by default in the General settings of Git Integration for Jira app.

Jira Data Center administrators can enable/disable this feature for all Jira users. All Jira Server users can enable the GitLens integration separately (see Profile settings)

Go to the Git Integration for Jira – **General settings** tab (sidebar).

Enable/disable this setting under **GitLens integration** section.

<img src='/wp-content/uploads/gij-gitserverdc-deeplink-gitlens-general-settings.png'  style='margin:25px auto;display:block;' alt='Access the GitLens integration option to enable/disable the feature in the General settings of the Git Integration for Jira app' />

<br>

<b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px 5px 0; font-size: small;'>GIT INTEGRATION: JIRA CLOUD</b> <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px 5px 0; font-size: small;'>COMING SOON</b>

User settings is added to support non-admin users to be able to enable/disable this feature.

&nbsp;

### See more Git Integration for Jira app features

[\>\> Deep Linking to the GitKraken Git client](/git-integration-for-jira-data-center/deep-linking-to-the-gitkraken-git-client-gij-self-managed)

**Deep Linking into GitLens** (this page)

---

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

[Cancel indexing](/git-integration-for-jira-data-center/cancel-indexing-revision-indexing-gij-self-managed/) (Git Integration for Jira Data Center)

[Pull request filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Tag filters](/git-integration-for-jira-data-center/tag-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Indexing queue viewer](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/) (Git Integration for Jira Data Center)

[Deep linking feature](/git-integration-for-jira-data-center/deeplinking-feature-gij-self-managed/) (Git Integration for Jira Data Center)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + ScriptRunner](/git-integration-for-jira-data-center/gij-plus-scriptrunner-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + Jira Automation](/git-integration-for-jira-data-center/git-integration-plus-jira-automation-gij-self-managed/) (Git Integration for Jira Data Center)

[Enforced git permissions for Jira users – Features](/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed/) (Git Integration for Jira Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/shared-reindex-queue-between-dc-nodes-gij-self-managed/) (Git Integration for Jira Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed/) (Git Integration for Jira Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/) (Git Integration for Jira Data Center)

[Issue Git integration panel – Features](/git-integration-for-jira-data-center/issue-git-integration-panel-gij-self-managed/) (Git Integration for Jira Data Center)

