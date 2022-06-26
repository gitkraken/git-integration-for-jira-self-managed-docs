---

title: Bitbucket Server
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <B>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/bitbucket-cloud-gij-cloud/'>See the corresponding article</a>.
    </div>
    </div>
</div>
<br>

![](https://bigbrassband.com/confluence/images/bitbucket-banner-logo.png)

# Integrate Bitbucket with Jira Data Center/Server

Quickly learn how to connect Bitbucket Server git repositories via Git Integration for Jira app.

- [Integrate Bitbucket with Jira Data Center/Server](#integrate-bitbucket-with-jira-data-centerserver)
  - [Single repository integration](#single-repository-integration)
  - [Setting up weblinks](#setting-up-weblinks)
  - [Viewing git commits in Jira Data Center/Server](#viewing-git-commits-in-jiradata-centerserver)

* * *

## Single repository integration

Obtain the repository URL from the Bitbucket Server repository project page. Choose between SSH or HTTPS.

1.  On your Jira dashboard menu, go to **Git** ➜ **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from BitBucket web portal in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Data Center/Server.

## Setting up weblinks

This feature is optional.

Configure web links from either of the following locations:

*   **Advanced setup** in Connect Wizard
*   Git ➜ Manage repositories ➜ **Edit repository/integration** settings.

Set git paths and customize options for the git host.

Save the changes.

## Viewing git commits in Jira Data Center/Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.

