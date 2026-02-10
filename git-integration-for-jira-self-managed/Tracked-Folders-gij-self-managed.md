---

title: Tracked Folders
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- integration guide -->

<img src='/wp-content/uploads/tracked-folder-mobile-custom3.png' width=367 height=82 style='max-width:100%' />

&nbsp;

## Integrate Tracked Folders with Jira Data Center

Quickly learn how to connect Tracked Folders via Git Integration for Jira Data Center app.

**What's on this page:**
- [Integrate Tracked Folders with Jira Data Center](#integrate-tracked-folders-with-jira-data-center)
  - [Limitations](#limitations)
  - [Introduction](#introduction)
  - [Connecting to a tracked folder](#connecting-to-a-tracked-folder)
  - [Folder depth setting](#folder-depth-setting)
  - [JMESPath filter setting](#jmespath-filter-setting)
  - [Editing a tracked folder](#editing-a-tracked-folder)
  - [Removing a tracked folder](#removing-a-tracked-folder)
  - [Resetting index](#resetting-index)
  - [Viewing tracked repositories](#viewing-tracked-repositories)
  - [Reindexing a tracked folder](#reindexing-a-tracked-folder)
  - [Viewing git commits in Jira Data Center](#viewing-git-commits-in-jira-data-center)
  - [Jira administrators](#jira-administrators)
    - [Solution 1](#solution-1)
    - [Solution 2](#solution-2)
  - [More Integration Guides](#more-integration-guides)

&nbsp;
* * *
&nbsp;

### Limitations

**Pros:**

*   Less storage is required (the repositories are not cloned to Jira).

**Cons:**

*   Only commits and branches get indexed with this method.
*   Pull/merge requests are not indexed with this method.
*   The create branch/pull request feature does not work.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <b>Add tracked folder</b> feature requires that Jira and the git servers be on the same filesystem. Make sure that the user that Jira is running with has access permissions to the path with the git repositories.
    </div>
    </div>
</div>

&nbsp;

### Introduction

This feature scans a locally accessible path for cloned Git repositories and automatically imports those Git repository references into Jira. A repository group called <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b> is added into the Git Integration for Jira app repository settings.

&nbsp;

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/npya1xi1pm?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px;'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/npya1xi1pm'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

### Connecting to a tracked folder

To add repositories via Tracked Folders:

<img src='/wp-content/uploads/gij-jira-dashboard-menu-git-gitmgr-sel.png' style='margin:25px auto;max-width:100%;display:block;' />

1.  Go to **Manage Git Repositories** (_Jira Dashboard_ ➜ **Git** menu) in Jira Data Center.

    ![](/wp-content/uploads/gij-gitmgr-connect2git-add-tracked-folder-access.png)

2.  Click the dropdown arrow on **Connect to Git Repository** then **Add tracked folder**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-jira-serverdc-tracked-folder-wizard-dlg-c.png)

    *   Enter the **Tracked folder location** in the required field. For this feature, a local path to the git repository residing on the same server as Jira is required. For example: `/home/ec2-user/repositories/*`.

    *   Set the **Folder Depth** according to your organization’s requirements. For more information on this feature, see the [Folder Depth section](#folder-depth-setting) below.

    *   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>OPTIONAL</b> Expand the <b>Advanced</b> twisty to set the <b>JMESPath</b> options (see <a href='#jmespath-filter-setting'>more details below</a>) to filter connected repositories to Jira.

3.  In the following dialog, the wizard will find git repositories stored in the provided path and displays the list of repositories found.

    ![](/wp-content/uploads/gij-jira-serverdc-tracked-folder-wizard-repo-found-c.png)

    In the above example repository root, `/home/ec2-user/repositories/*`, all repositories under this mask (`/home/ec2-user/repositores/TestGitPluginRepo`, `/home/ec2-user/repositores/emptyRepo`, … , `/home/ec2-user/repositores/jira-git-plugin`) will be handled as one entry in the **Manage Git repositories** configuration page. For other features, these are treated as separate repositories.

4.  The Add tracked folder wizard scans the local path one folder level deep or depending on the **Folder Depth** setting. Click **Import repositories**.
    The wizard automatically adds the detected repositories to Jira. If a repository is added to the path, Jira will add it to the index. If a repository is removed from the path, Jira will drop the index for that repository.

5.  On the **Settings** dialog, set **Repository Browser, Smart Commits** and **Project Association** permissions, if required. Click **Next**.

6.  Click **Finish** to complete adding the tracked folder.


The tracked folder is added to the repository configuration list.

You can add multiple tracked folders in case your repositories are spread among multiple locations.

&nbsp;

### Folder depth setting

GitLab 13+ switched to hashed storage as the default. Git Integration for Jira app also supports this move by implementing support to tracked repositories with a new folder depth option for the GitLab hashed storage.

In GitLab 13.0, hashed storage is enabled by default and the legacy storage is deprecated. Support for legacy storage will be removed in GitLab 14.0.

The default tracked folder depth value is **1**. For GitLab hashed storage support, our recommended setting is **3**.

See <a href='https://docs.gitlab.com/ee/administration/repository_storage_paths.html' target='_blank'><b>GitLab docs on Hashed Storage</b></a> for detailed information.

&nbsp;

### JMESPath filter setting

This optional setting is a filter on how repositories are listed and displayed.

The following examples of JMESPath filters work for any tracked folder integration including GitLab hashed storage folders (Connect to Git Repository ➜ _**Add tracked folder**_):

**Lists repositories with names containing "git"**

```java
[?contains(name, 'git')]
```

**Lists all the repositories that contain the specified names**

```java
[?contains(name, 'git') \| contains(name, 'Slap') \| contains(name, 'est')]
```

**Excludes repositories with names that contain words 'firstword' and 'secondword'**

```java
[?!contains(name, 'firstword') \| contains(name, 'secondword')]
```

The example below ONLY works for tracked folder integration; where it supports the ‘`fullPath`’ field:

**Excludes repositories from the sub-folder**

```java
[?!starts_with(fullPath, '/home/user/local/store/private-repos')]
```

&nbsp;

### Editing a tracked folder

On the **Manage Git repositories** settings page, click ![](/wp-content/uploads/actions-icon.png) Actions  ➜ **Edit tracked folder** to modify tracked folder git repository settings.

![](/wp-content/uploads/gij=jira-serverdc-tracked-folder-git-edit.png)

&nbsp;

### Removing a tracked folder

On the **Git Repositories** settings page, click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Delete tracked folder** to remove the tracked folder configuration from Jira.

A confirmation prompt will be displayed. Clicking **Remove** will only remove the tracked folder setting from the repository configuration list. The local path for this tracked folder will not be deleted and will still remain in the local system for later use.

&nbsp;

### Resetting index

On the **Git Repositories** settings page, click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Reset index**.

This action will reset the indexes of the repositories for the selected tracked folder.

&nbsp;

### Viewing tracked repositories

On the **Git Repositories** settings page, click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Show tracked repositories**.

This action will open the **Tracked Folder** dialog showing the tracked repositories.

The Repository Browser will not display the repository if it is disabled in the Git Repositories configuration. The commits and code diffs in the **Issue** ➜ **Git Commits**, **Git Roll Up** and **Project** tabs will also be unavailable due to this.

&nbsp;

### Reindexing a tracked folder

On the **Manage Git repositories** settings page, click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Reindex tracked folder**.

This action will perform a reindex of the selected tracked folder.

If a new repository is manually added into the local path, the Git Integration for Jira app will detect the new repository folder on the next reindex and add it into the existing tracked folder in Jira.

If a repository folder is manually deleted from the local path, the Git Integration for Jira app will remove the repository setting from the tracked folder in Jira on the next reindex.

&nbsp;

### Viewing git commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.

&nbsp;

### Jira administrators

It is possible to track all repositories hosted on a GitLab server from inside a Jira server:

1.  Setup NFS server on the GitLab computer

2.  Mount GitLab repositories folder as a remote NFS folder on Jira server

3.  Configure NFS permissions to allow Jira to access GitLab folders by using either of the two possible solutions:

&nbsp;

#### Solution 1

The `'all_squash'` option must not be used in the NFS server **'etc/exports'** file for GitLab folders. The NFS client should have the **'git'** group with the same GID as the **'git'** group on the NFS server. The Jira user on the NFS client should be added to the group **'git'**.

**Example of '/etc/exports' line:**

```java
/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,root_squash,async)
```

#### Solution 2

Use the `'all_squash,async,anonuid=$uid,anongid=$gid'` option on the NFS server, where _$uid_ and _$gid_ are the user ID and group ID for **'git'** user and **'git'** group respectively _(or another user/group which you are using to access GitLab repositories on GitLab server)_.

```java
/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,all_squash,async,anonuid=497,anongid=497)
```

In both cases either `'ro'` or `'rw'` options may be used on the NFS server.

&nbsp;
* * *

### More Integration Guides

[GitHub.com](/git-integration-for-jira-data-center/gitHub-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub Enterprise Server](/git-integration-for-jira-data-center/gitHub-Enterprise-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab.com](/git-integration-for-jira-data-center/gitLab-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab CE/EE](/git-integration-for-jira-data-center/gitLab-com-CE-EE-gijsm-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Azure DevOps \| Visual Studio Team Services (VSTS)](/git-integration-for-jira-data-center/azure-DevOps-Visual-Studio-Team-Services-(VSTS)-gij-self-managed) (Git Integration for Data Center/Jira Server)

[Azure DevOps Server \| Team Foundation Services (TFS)](/git-integration-for-jira-data-center/azure-DevOps-Server-Team-Foundation-Services-(TFS)-gij-self-managed) (Git Integration for Jira Data Center/Server)

[AWS CodeCommit](/git-integration-for-jira-data-center/aws-codecommit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Gerrit](/git-integration-for-jira-data-center/gerrit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bitbucket Server](/git-integration-for-jira-data-center/Bitbucket-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bonobo](/git-integration-for-jira-data-center/bonobo-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Windows Network \| Server Share](/git-integration-for-jira-data-center/Windows-Network-Server-Share-gij-self-managed) (Git Integration for Jira Data Center/Server)

**Tracked Folders** (this page)

[**Back to:** Integration basics](/git-integration-for-jira-data-center/Integration-Basics-gij-self-managed) (Git Integration for Jira Data Center/Server)


