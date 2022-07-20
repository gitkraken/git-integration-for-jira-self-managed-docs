---

title: Why don't I see commits? (Data Center)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/2041937935/Asset%202@5x_1.png?version=1&modificationDate=1640251774847&cacheVersion=1&api=v2)

<p style='text-align: center'>↓</p>

**\> Check if Git Integration for Jira app is installed, licensed and active** (JIRA ADMIN)

Follow the [link](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=overview) to install from the Atlassian Marketplace. You can verify that the Git Integration for Jira Data Center app is installed by visiting:

Jira Administration ➜ **Manage apps**.

Verify that the license is valid and that the application is active (installed, subscription is active).

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/gitserver-jira-manage-apps-page.png?version=1&modificationDate=1640254878878&cacheVersion=1&api=v2&width=800&height=530) 

<p style='text-align: center'>Git Integration for Jira Data Center is installed, licensed and active</p>

<p style='text-align: center'>↓</p>

**\> Is Integration/repository enabled?** (JIRA ADMIN)

Repo or integration level:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/is-repo-enabled-repo-level.png?version=1&modificationDate=1640251773616&cacheVersion=1&api=v2&width=800&height=388)

<br>

Repo within integration:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/server-1.png?version=1&modificationDate=1640251777855&cacheVersion=1&api=v2&width=800&height=388)

<p style='text-align: center'>Integration/Repository is enabled</p>

<p style='text-align: center'>↓</p>

**\> Is the Git commits issue tab enabled by the Jira administrator in General Settings?** (JIRA ADMIN)

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/jira-server-dc-general-settings-whycommits(c).png?version=1&modificationDate=1640251773360&cacheVersion=1&api=v2&width=800&height=483)

<p style='text-align: center'>Git commits issue tab is enabled</p>

<p style='text-align: center'>↓</p>

**\> Check if repository has been reindexed since commit** (JIRA ADMIN)

Reindexing integrations (or repositories) manually. Note: all repositories are updated regularly without any manual updating required.

Approximately every 8-15 minutes.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/reindex-manually.png?version=1&modificationDate=1640251775591&cacheVersion=1&api=v2&width=800&height=388)

<br>

Admins can setup webhooks to index commits immediately

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/gitserver-webhooks-page-example.png?version=1&modificationDate=1640255569660&cacheVersion=1&api=v2&width=800&height=490)

<p style='text-align: center'>The repository has indexed since the commit was pushed</p>

<p style='text-align: center'>↓</p>

**\> Reset the index in Manage Git repositories** (JIRA ADMIN)

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/reset-index.png?version=1&modificationDate=1640251778112&cacheVersion=1&api=v2&width=800&height=388)

<p style='text-align: center'>It didn't help</p>

<p style='text-align: center'>↓</p>

**\> Check if repository with commit is connected to Jira** (JIRA ADMIN)

A couple ways to do this:

*   Via integration in Manage Git Repositories

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/via-repo-1.png?version=1&modificationDate=1640251777376&cacheVersion=1&api=v2&width=800&height=388)

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/via-repo-2.png?version=1&modificationDate=1640251777622&cacheVersion=1&api=v2&width=800&height=388)

<br>

*   Via Repository Browser (shows the list of all the repositories that are connected in one list):

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/reindex-since-commit.png?version=1&modificationDate=1640251777125&cacheVersion=1&api=v2&width=800&height=388)

<p style='text-align: center'>The repository with the missing commit is connected</p>

<p style='text-align: center'>↓</p>

**\> Check if repository is associated with Jira project** (JIRA ADMIN)

It allows an admin to associate an integration (and all the repositories) or just a single repository to a set of Jira projects (one, many, or all).

Go to Manage Git Repositories → Project Permissions.

Check "Associate all projects" if you want the repository to be associated with all Jira projects.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/associate-projects.png?version=1&modificationDate=1640251775353&cacheVersion=1&api=v2&width=800&height=388)

<p style='text-align: center'>The Jira project is associated with the repository</p>

<p style='text-align: center'>↓</p>

**\> Check if commit has a valid Jira issue key**

Valid commit Jira issue key looks like **ABC-123 added a bug fix** or **MAIN-345 adding important new feature**.

The key is that the Jira issue key is in the commit message. The valid Jira issue key example is shown on the screenshot:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/valid-key.png?version=1&modificationDate=1640251776341&cacheVersion=1&api=v2&width=800&height=388)

<br>

GitLab showing an actual commit and the commit message:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/gitlab.png?version=1&modificationDate=1640251778362&cacheVersion=1&api=v2&width=800&height=388)

Check the video for more instructions:

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/7kj43knu4m?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/7kj43knu4m'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<br>

<p style='text-align: center'>Commit has a valid Jira issue key</p>

<p style='text-align: center'>↓</p>

**\> Check if user has “Development Tools” permission** (JIRA ADMIN)

Using the **Permission Helper** within Jira Server - verify that the user in question has the **Development Tools** permission.

The Permission Helper is available to Jira admins: Jira Administration ➜ System ➜ **Permission Helper**.

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/ynjggc2wzg?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/ynjggc2wzg'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<p style='text-align: center'>Permissions are correct</p>

<p style='text-align: center'>↓</p>

**\> Check** if commit is showing now

Where you can see commits:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2041937935/new-jira.png?version=1&modificationDate=1640251776096&cacheVersion=1&api=v2&width=800&height=388)

<p style='text-align: center'>Commit isn't shown<p>

<p style='text-align: center'>↓</p>

Contact [support@bigbrassband.com](mailto:support@bigbrassband.com) by email or via the [BigBrassBand Support Portal](https://bigbrassband.atlassian.net/servicedesk/customer/portals)

