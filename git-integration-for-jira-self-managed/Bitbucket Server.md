---

title: Bitbucket Server
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---



Using **Jira Cloud**? [See the corresponding article](/wiki/spaces/GITCLOUD/pages/86343820/Bitbucket+Cloud).

![](https://bigbrassband.com/confluence/images/bitbucket-banner-logo.png)

**Integrate Bitbucket with Jira Data Center**



Quickly learn how to connect Bitbucket Server git repositories via Git Integration for Jira app.

**What's on this page:**



* * *

## **Single Repository**

Obtain the repository URL from the Bitbucket Server repository project page.  Choose between SSH or HTTPS.

1.  On your Jira dashboard menu, go to **Git** > **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from BitBucket web portal in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Data Center.



## **Setting Up Weblinks**

This feature is optional.

Configure web links from either of the following locations:

*   **Advanced setup** in Connect Wizard
*   **Git** > **Manage repositories** > **Edit repository/integration** settings.

Set git paths and customize options for the git host.

Save the changes.



## **Viewing Git Commits in Jira Data Center**

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.





* * *

## More Integration Guides

page icon as list [Integrate GitHub.com with Jira Data Center](/wiki/spaces/GIJDC/pages/91979804/GitHub.com)

page icon as list [Integrate GitHub Enterprise with Jira Data Center](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server)

page icon as list [Integrate GitLab.com with Jira Data Center](/wiki/spaces/GIJDC/pages/91881531/GitLab.com)

page icon as list [Integrate GitLab CE/EE with Jira Data Center](/wiki/spaces/GIJDC/pages/91947056)

page icon as list [Integrate Azure DevOps/VSTS with Jira Data Center](/wiki/spaces/GIJDC/pages/92176406)

page icon as list [Integrate Azure DevOps Server/TFS with Jira Server](/wiki/spaces/GITSERVER/pages/80904193)

page icon as list [Integrate AWS CodeCommit with Jira Data Center](/git-integration-for-jira-self-managed/AWS-CodeCommit)

page icon as list [Integrate Gerrit with Jira Data Center](/git-integration-for-jira-self-managed/Gerrit)

page icon as list [Integrate Bonobo with Jira Data Center](/git-integration-for-jira-self-managed/Bonobo)

page icon as list [Integrate Tracked Folders with Jira Data Center](/git-integration-for-jira-self-managed/Tracked-Folders)

page icon as list [Integrate Windows Network/Server Share with Jira Data Center](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/81035265)