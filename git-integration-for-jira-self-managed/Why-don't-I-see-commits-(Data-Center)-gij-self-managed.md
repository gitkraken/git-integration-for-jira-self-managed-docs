---

title: Why don't I see commits? (Data Center)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/2041937935/Asset%202@5x_1.png?version=1&modificationDate=1640251774847&cacheVersion=1&api=v2)



JIRA ADMIN

 Check if Git Integration for Jira app is installed, licensed and active

Follow the [link](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=overview) to install from the Atlassian Marketplace. You can verify that the Git Integration for Jira Data Center app is installed by visiting:

Jira Administration ➜ Manage apps.

Verify that the license is valid and that the application is active (installed, subscription is active).   

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/gitserver-jira-manage-apps-page.png?version=1&modificationDate=1640254878878&cacheVersion=1&api=v2&width=800&height=530) 

Git Integration for Jira Data Center is installed, licensed and active

JIRA ADMIN

 Is Integration/repository enabled?

Repo or integration level:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/is-repo-enabled-repo-level.png?version=1&modificationDate=1640251773616&cacheVersion=1&api=v2&width=800&height=388)

Repo within integration:    

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/server-1.png?version=1&modificationDate=1640251777855&cacheVersion=1&api=v2&width=800&height=388)

Integration/Repository is enabled

JIRA ADMIN

 Is the Git commits issue tab enabled by the Jira administrator in General Settings?

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/jira-server-dc-general-settings-whycommits(c).png?version=1&modificationDate=1640251773360&cacheVersion=1&api=v2&width=800&height=483)

Git commits issue tab is enabled

JIRA ADMIN

 Check if repository has been reindexed since commit

Reindexing integrations (or repositories) manually. Note: all repositories are updated regularly without any manual updating required.

Approximately every 8-15 minutes.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/reindex-manually.png?version=1&modificationDate=1640251775591&cacheVersion=1&api=v2&width=800&height=388)

Admins can setup webhooks to index commits immediately

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/gitserver-webhooks-page-example.png?version=1&modificationDate=1640255569660&cacheVersion=1&api=v2&width=800&height=490)

The repository has indexed since the commit was pushed

JIRA ADMIN

 Reset the index in Manage Git repositories

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/reset-index.png?version=1&modificationDate=1640251778112&cacheVersion=1&api=v2&width=800&height=388)

It didn't help

JIRA ADMIN

 Check if repository with commit is connected to Jira

A couple ways to do this:

*   Via integration in Manage Git Repositories

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/via-repo-1.png?version=1&modificationDate=1640251777376&cacheVersion=1&api=v2&width=800&height=388)

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/via-repo-2.png?version=1&modificationDate=1640251777622&cacheVersion=1&api=v2&width=800&height=388)

*   Via Repository Browser (shows the list of all the repositories that are connected in one list):

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/reindex-since-commit.png?version=1&modificationDate=1640251777125&cacheVersion=1&api=v2&width=800&height=388)

The repository with the missing commit is connected

JIRA ADMIN

 Check if repository is associated with Jira project

It allows an admin to associate an integration (and all the repositories) or just a single repository to a set of Jira projects (one, many, or all).

Go to Manage Git Repositories → Project Permissions. 

Check "Associate all projects" if you want the repository to be associated with all Jira projects.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/associate-projects.png?version=1&modificationDate=1640251775353&cacheVersion=1&api=v2&width=800&height=388)

The Jira project is associated with the repository

 Check if commit has a valid Jira issue key

Valid commit Jira issue key looks like **ABC-123 added a bug fix** or **MAIN-345 adding important new feature**.

The key is that the Jira issue key is in the commit message. The valid Jira issue key example is shown on the screenshot:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/valid-key.png?version=1&modificationDate=1640251776341&cacheVersion=1&api=v2&width=800&height=388)

GitLab showing an actual commit and the commit message:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/gitlab.png?version=1&modificationDate=1640251778362&cacheVersion=1&api=v2&width=800&height=388)



Check the video for more instructions:



Right-click [here](https://bigbrassband.wistia.com/medias/7kj43knu4m) and view this video in a new browser tab.

Commit has a valid Jira issue key

JIRA ADMIN

 Check if user has “Development Tools” permission

Using the **Permission Helper** within Jira Server - verify that the user in question has the **Development Tools** permission.

The Permission Helper is available to Jira admins: Jira Administration ➜ System ➜ **Permission Helper**.





Right-click [here](https://bigbrassband.wistia.com/medias/ynjggc2wzg) and view this video in a new browser tab.

Permissions are correct

 Check if commit is showing now

Where you can see commits:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/new-jira.png?version=1&modificationDate=1640251776096&cacheVersion=1&api=v2&width=800&height=388)

Commit isn't shown

Contact [support@bigbrassband.com](mailto:support@bigbrassband.com) by email or via the [BigBrassBand Support Portal](https://bigbrassband.atlassian.net/servicedesk/customer/portals)