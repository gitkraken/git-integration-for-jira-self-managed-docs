---

title: Why don't I see commits? (Data Center)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<img src='/wp-content/uploads/gij-troubleshoot-how-do-i-see-commits-top.png' style='margin:25px auto;max-width:100%;display:block;' />

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if Git Integration for Jira app is installed, licensed and active

Follow the [link](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=overview) to install from the Atlassian Marketplace. You can verify that the Git Integration for Jira Data Center app is installed by visiting:

Jira Administration ➜ **Manage apps**.

Verify that the license is valid and that the application is active (installed, subscription is active).

<img src='/wp-content/uploads/gij-gitserver-jira-manage-apps-page.png' style='margin:25px auto;max-width:100%;display:block;' />

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>Git Integration for Jira Data Center is installed, licensed and active</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Is Integration/repository enabled?

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

Repo or integration level:

![](/wp-content/uploads/gij-gitserver-idontsee-commits-is-repo-enabled-repo-level.png)

Repo within integration:

![](/wp-content/uploads/gij-gitserver-idontsee-commits-is-repo-enabled-repo-within-integration.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>Integration/repository is enabled</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Is the Git commits issue tab enabled by the Jira administrator in General Settings?

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

![](/wp-content/uploads/gij-gitserver-commits-issue-tab-enabled-admin.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>Git commits issue tab is enabled</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if repository has been reindexed since commit

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

Reindexing integrations (or repositories) manually. Note: all repositories are updated regularly without any manual updating required.

Approximately every 8-15 minutes.

![](/wp-content/uploads/gij-gitserver-repo-reindex-manually.png)

Admins can setup webhooks to index commits immediately

![](/wp-content/uploads/gij-gitserver-webhooks-page-example.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>The repository has indexed since the commit was pushed</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Reset the index in Manage Git repositories

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

![](/wp-content/uploads/gij-gitserver-repo-reset-index.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>It didn't help</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if repository with commit is connected to Jira

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

A couple ways to do this:

*   Via integration in Manage Git Repositories

    ![](/wp-content/uploads/gij-gitserver-gitmgr-actions-via-repo-1.png)

    ![](/wp-content/uploads/gij-gitserver-gitmgr-actions-via-repo-2.png)

*   Via Repository Browser (shows the list of all the repositories that are connected in one list):

    ![](/wp-content/uploads/gij-gitserver-gitmgr-reindex-since-commits.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>The repository with the missing commit is connected</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if repository is associated with Jira project

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

It allows an admin to associate an integration (and all the repositories) or just a single repository to a set of Jira projects (one, many, or all).

1.  Go to Manage Git Repositories.
2.  On proposed integration/repository, go to &nbsp;![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit integration feature settings**.
3.  Scroll down to **Project Permissions** and assign specific integration/repository associations on the provided box.

![](/wp-content/uploads/gij-gitserver-gitmgr-repo-assoc-manual.png)

Check the **Associate all projects** setting if you want the repository to be associated with all Jira projects.

![](/wp-content/uploads/gij-gitserver-gitmgr-repo-assoc-all.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align:center'>The Jira project is associated with the repository</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if commit has a valid Jira issue key

Valid commit Jira issue key looks like **ABC-123 added a bug fix** or **MAIN-345 adding important new feature**.

The key is that the Jira issue key is in the commit message. The valid Jira issue key example is shown on the screenshot:

![](/wp-content/uploads/gij-gitserver-example-jira-valid-key.png)

GitLab showing an actual commit and the commit message:

![](/wp-content/uploads/gij-gitlab-showing-actual-commit-and-msg-example.png)

Check the video for more instructions:

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/7kj43knu4m?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/7kj43knu4m'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<p style='text-align:center;font-size:20px;margin-top:20px;'>&#8681;</p>

<p style='text-align:center'>Commit has a valid Jira issue key</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if user has “Development Tools” permission

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA ADMIN</b>

Using the **Permission Helper** within Jira Server - verify that the user in question has the **Development Tools** permission.

The Permission Helper is available to Jira admins: Jira Administration ➜ System ➜ **Permission Helper**.

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/ynjggc2wzg?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:12px;margin-bottom:20px;'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/ynjggc2wzg'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align: center'>Permissions are correct</p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

#### \> Check if commit is showing now

Where you can see commits:

![](/wp-content/uploads/gij-gitserver-commits-now-showing.png)

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p style='text-align: center'>Commit still isn't showing up<p>

<p style='text-align:center;font-size:20px'>&#8681;</p>

<p align=center>Contact <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a> by email or via the <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>GIJ Support Portal</a>.</p>

