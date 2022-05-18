---

title: Tracked Folders
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91947120/tracked-folders-banner-logo2.png?version=1&modificationDate=1611969637784&cacheVersion=1&api=v2&width=340&height=79)

# Integrate Tracked Folders with Jira Data Center


Quickly learn how to connect Tracked Folders via Git Integration for Jira Data Center app.

**What's on this page:**

* * *

## Limitations

|     |
| --- |
| **Pros** |
| *   Less storage is required (the repositories are not cloned to Jira). |
| **Cons** |
| *   Only commits and branches get indexed with this method.<br>    <br>*   Pull/merge requests are not indexed with this method.<br>    <br>*   The create branch/pull request feature does not work. |

The **Add tracked folder** feature requires that Jira and the git servers be on the same filesystem.  Make sure that the user that Jira is running with has access permissions to the path with the git repositories.

## Introduction

Introduced in **v2.9.0** of the Git Integration for Jira app, this feature scans a locally accessible path for cloned Git repositories and automatically imports those Git repository references into Jira. A repository group called FOLDER is added into the Git Integration for Jira app repository settings.

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/npya1xi1pm) _and view this video in a new tab/window._

## Connecting to a tracked folder

To add repositories via Tracked Folders:

1.  Go to **Manage Git Repositories** (_Jira Dashboard_ ➜ **Git** menu) in Jira Data Center.

2.  Click the dropdown arrow on **Connect to Git Repository** then **Add tracked folder**. The following dialog is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/91947120/jira-serverdc-tracked-folder-wizard-dlg(c).png?version=1&modificationDate=1611969638590&cacheVersion=1&api=v2)
    *   Enter the **Tracked folder location** in the required field. For this feature, a local path to the git repository residing on the same server as Jira is required. For example: `/home/ec2-user/repositories/*`.

    *   Set the **Folder Depth** according to your organization’s requirements. For more information on this feature, see the [**Folder Depth section**](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/81002508/Tracked+Folders#Folder-depth-setting) below.

    *   _Optional._ Expand the **Advanced** twisty to set the **JMESPath** options (see [more details below](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/81002508/Tracked+Folders#JMESPath-filter-setting)) to filter connected repositories to Jira.

3.  In the following dialog, the wizard will find git repositories stored in the provided path and displays the list of repositories found.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/91947120/jira-serverdc-tracked-folder-wizard-repo-found(c).png?version=1&modificationDate=1611969639612&cacheVersion=1&api=v2)

    In the above example repository root, `/home/ec2-user/repositories/*`, all repositories under this mask (`/home/ec2-user/repositores/TestGitPluginRepo`, `/home/ec2-user/repositores/emptyRepo`, … , `/home/ec2-user/repositores/jira-git-plugin`) will be handled as one entry in the **Git Repositories** configuration page. For other features, these are treated as separate repositories.

4.  The Add tracked folder wizard scans the local path one folder level deep or depending on the **Folder Depth** setting. Click **Import repositories**.
    The wizard automatically adds the detected repositories to Jira. If a repository is added to the path, Jira will add it to the index. If a repository is removed from the path, Jira will drop the index for that repository.

5.  On the **Settings** dialog, set **Repository Browser, Smart Commits** and **Project Association** permissions, if required. Click **Next**.

6.  Click **Finish** to complete adding the tracked folder.


The tracked folder is added to the repository configuration list.

You can add multiple tracked folders in case your repositories are spread among multiple locations.

## Folder depth setting

GitLab 13+ switched to hashed storage as the default. Git Integration for Jira app also supports this move by implementing support to tracked repositories with a new folder depth option for the GitLab hashed storage.

In GitLab 13.0, hashed storage is enabled by default and the legacy storage is deprecated. Support for legacy storage will be removed in GitLab 14.0.

The default tracked folder depth value is **1**. For GitLab hashed storage support, our recommended setting is **3**.

See [**GitLab docs on Hashed Storage**](https://docs.gitlab.com/ee/administration/repository_storage_types.html#hashed-storage) for detailed information.

## JMESPath filter setting

This optional setting is a filter on how repositories are listed and displayed.

The following examples of JMESPath filters work for any tracked folder integration including GitLab hashed storage folders (Connect to Git Repository ➜ _**Add tracked folder**_):

|     |
| --- |
| ### Lists repositories with names containing "git" |
| ```java<br>[?contains(name, 'git')]<br>``` |

|     |
| --- |
| ### Lists all the repositories that contain the specified names |
| ```java<br>[?contains(name, 'git') \| contains(name, 'Slap') \| contains(name, 'est')]<br>``` |

|     |
| --- |
| ### Excludes repositories with names that contain words 'firstword' and 'secondword' |
| ```java<br>[?!contains(name, 'firstword') \| contains(name, 'secondword')]<br>``` |

The example below ONLY works for tracked folder integration; where it supports the ‘`fullPath`’ field:

|     |
| --- |
| ### Excludes repositories from the sub-folder |
| ```java<br>[?!starts_with(fullPath, '/home/user/local/store/private-repos')]<br>``` |

## Editing a tracked folder

On the **Git Repositories** settings page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions**  ➜ **Edit tracked folder** to modify tracked folder git repository settings.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/91947120/jira-serverdc-tracked-folder-git-edit.png?version=1&modificationDate=1611969640211&cacheVersion=1&api=v2)

## Removing a tracked folder

On the **Git Repositories** settings page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** ➜ **Delete tracked folder** to remove the tracked folder configuration from Jira.

A confirmation prompt will be displayed. Clicking **Remove** will only remove the tracked folder setting from the repository configuration list. The local path for this tracked folder will not be deleted and will still remain in the local system for later use.

## Resetting index

On the **Git Repositories** settings page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** ➜ **Reset index**.

This action will reset the indexes of the repositories for the selected tracked folder.

## Viewing tracked repositories

On the **Git Repositories** settings page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** ➜ **Show tracked repositories**.

This action will open the **Tracked Folder** dialog showing the tracked repositories.

The Repository Browser will not display the repository if it is disabled in the Git Repositories configuration. The commits and code diffs in the **Issue** ➜ **Git Commits**, **Git Roll Up** and **Project** tabs will also be unavailable due to this.

## Reindexing a tracked folder

On the **Git Repositories** settings page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** ➜ **Reindex tracked folder**.

This action will perform a reindex of the selected tracked folder.

If a new repository is manually added into the local path, the Git Integration for Jira app will detect the new repository folder on the next reindex and add it into the existing tracked folder in Jira.

If a repository folder is manually deleted from the local path, the Git Integration for Jira app will remove the repository setting from the tracked folder in Jira on the next reindex.

## Viewing git commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.


## Jira administrators ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png)

It is possible to track all repositories hosted on a GitLab server from inside a Jira server:

1.  Setup NFS server on the GitLab computer

2.  Mount GitLab repositories folder as a remote NFS folder on Jira server

3.  Configure NFS permissions to allow Jira to access GitLab folders by using either of the two possible solutions:


|     |
| --- |
| ### **Solution 1** |
| The `'all_squash'` option must not be used in the NFS server **'etc/exports'** file for GitLab folders. The NFS client should have the **'git'** group with the same GID as the **'git'** group on the NFS server. The Jira user on the NFS client should be added to the group **'git'**. |
| **Example of '/etc/exports' line:**<br><br>```java<br>/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,root_squash,async)<br>``` |

|     |
| --- |
| ### **Solution 2** |
| Use the `'all_squash,async,anonuid=$uid,anongid=$gid'` option on the NFS server, where _$uid_ and _$gid_ are the user ID and group ID for **'git'** user and **'git'** group respectively _(or another user/group which you are using to access GitLab repositories on GitLab server)_. |
| ```java<br>/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,all_squash,async,anonuid=497,anongid=497)<br>``` |
| In both cases either `'ro'` or `'rw'` options may be used on the NFS server. |

## More integration guides

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate GitHub.com with Jira Data Center](/wiki/spaces/GIJDC/pages/91979804/GitHub.com)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate GitHub Enterprise with Jira Data Center](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate GitLab.com with Jira Data Center](http://gitlab.com)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate GitLab CE/EE with Jira Data Center](/wiki/spaces/GIJDC/pages/91947056)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Azure DevOps/VSTS with Jira Data Center](/wiki/spaces/GIJDC/pages/92176406)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Azure DevOps Server/TFS with Jira Data Center](/wiki/spaces/GIJDC/pages/91979843)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate AWS CodeCommit with Jira Data Center](/git-integration-for-jira-self-managed/AWS-CodeCommit)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Gerrit with Jira Data Center](/wiki/spaces/GIJDC/pages/91979855/Gerrit)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Bitbucket with Jira Data Center](/git-integration-for-jira-self-managed/Bitbucket-Server)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Bonobo with Jira Data Center](/wiki/spaces/GIJDC/pages/91947111/Bonobo)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Windows Network/Server Share with Jira Data Center](/wiki/spaces/GIJDC/pages/91881564/Windows+Network+%7C+Server+Share)

![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [Integrate Tracked Folders with Jira Data Center](/git-integration-for-jira-self-managed/Tracked-Folders)