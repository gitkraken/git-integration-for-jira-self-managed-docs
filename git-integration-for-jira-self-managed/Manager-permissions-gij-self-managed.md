---

title: Manager permissions
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class='embed-container embed-container--16-9'>
        <iframe width='709' height='382' src='https://www.youtube.com/embed/2tmWvRxj9Ls' frameborder='0' allowfullscreen ></iframe>
    </div>

<div align='center' style='margin-top:12px;margin-bottom:40px;'>
    <i>Right click <a href='https://www.youtube.com/watch?v=2tmWvRxj9Ls'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

This functionality is designed for Jira administrators as it reduces their workload. It enables assigned users to manage the Git Integration for Jira app without granting them full Jira admin privileges.

Before, only Jira admins could manage the Git Integration for Jira app. With this new feature, Jira admins can now select other Jira users (who are not administrators) and grant them permissions to manage integrations, add/remove/update, and manage apps.

With Manager permissions:

*   Share Git Integration for Jira app control with other (non-admin) Jira users

*   Change app settings, add/update integrations

*   Manage user roles through Jira Global Permissions

*   Managers are allowed to create integrations with project mapping settings.

&nbsp;

### Getting started

The Git Integration for Jira sidebar menu now includes a new item called **88**.

1.  On your Jira dashboard menu, go to Apps ➜ Git Integration: Manage integrations ➜ **Manager permissions**. (As an admin)

    ![](/wp-content/uploads/gij-datacenter-manager-permissions-access-loc.png)
    
    The first time you access the Manager permissions page, no active managers will be displayed. However, as you add more users, you will begin to see this list populate.
    
    &nbsp;

2.  Click on the **Admin \> Groups** label link on the Manager permissions page to take you to the Groups page.

    ![](/wp-content/uploads/gij-datacenter-manager-permissions-add-group.png)

    &nbsp;

3.  You can create a new group or use an existing group on the Groups page.

    ![](/wp-content/uploads/gij-datacenter-manager-permissions-add-new-group.png)

    *   Enter the group **Name** under the Add group section as required. For this guide, enter "GIJ Managers".
    
    *   Click **Add group** to create this new group for managers.

    This creates the specified group and displays it in the Groups list.

    &nbsp;

4.  To add members for the GIJ managers group, click **Edit members**.

    ![](/wp-content/uploads/gij-datacenter-manager-permissions-edit-group-members.png)

    Add qualified members to this group in order to as sist with managing GIJ features, in addition to the administrator. Do note that Jira administrators retain complete control over the system.

5.  Switch to the Manager permissions page (browser tab) then click **System \> Global permissions**.

    ![](/wp-content/uploads/gij-datacenter-manager-permissions-global-perms.png)

    &nbsp;

6.  On the Global permissions screen, the page is automatically scrolled to the **Grant Permission** section.

    ![](/wp-content/uploads/gij-datacenter-manager-permissions-global-add-perms.png)

    On the Add permission section:

    *   Select a **Permission** from the list. This feature adds a new global permission to your Jira instance. For this guide, choose **_Manage Git Integration for Jira by GitKraken_**.

    *   Select a **Group** from the list. For this case, choose the group that you created previously (GIJ Managers).

7.  Click **Add** to continue.

8.  Examine the **_Manage Git Integration for Jira by GitKraken_** global permission to see the roles that have been assigned to it:

![](/wp-content/uploads/gij-datacenter-manager-permissions-global-perms-sel.png)

&nbsp;

9.  Switch back to the **Manager permission** page to see the recently active managers list.

![](/wp-content/uploads/gij-datacenter-manager-permissions-manager-list.png)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Recent active managers gets populated for every user that is added to the GIJ Manager group.
    </div>
    </div>
</div>

&nbsp;

### What do users with the manager role have access to?

Every user you add to the GIJ Managers group will have complete access to the Git Integration for Jira app configuration, which includes the ability to modify settings and add/manage integrations.

GIJ Managers are allowed to create integrations and set project mapping settings with it. This also works with any git integration wizard in the Manage integrations page.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the manager is not the author of the added integration, then the project association settings are inaccessible via UI or API.<br>
        <img src='/wp-content/uploads/gij-datacenter-manager-permissions-project-mapping-edit.png' style='margin:10px auto 0px auto;display:block;max-width:100%;'>
    </div>
    </div>
</div>

**GIJ Managers** does not have the ability to change permissions or access the Manager permissions page. The managers also does not have the ability to change project visibility settings. This level of access is exclusively reserved for Jira admins.

![](/wp-content/gij-datacenter-manager-permissions-manage-mode.png)

&nbsp;

### What will the non-admin users see when trying to access Git Integration for Jira app?

Non-admin users will not be able to see or access the Git Integration for Jira app configuration or the Manger permissions pages.

![](/wp-content/uploads/gij-datacenter-manager-permissions-user-mode.png)

&nbsp;

### See more Git Integration for Jira app features

**Manager permissions** (this page)

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

