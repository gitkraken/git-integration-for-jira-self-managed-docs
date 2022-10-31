---

title: Windows Network | Server Share
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<img src='/wp-content/uploads/gij-win-network-server-share-banner-logo.png' width=600 height=80 />

<br>

# Integrate Windows Network/Server Share with Jira Data Center

Quickly learn how to connect Windows Network or Server Share via Git Integration for Jira app.

**What's on this page:**
- [Integrate Windows Network/Server Share with Jira Data Center](#integrate-windows-networkserver-share-with-jiradata-center)
  - [Adding a Repository Hosted on Window Servers or Network Share](#adding-a-repository-hosted-on-window-servers-or-network-share)
  - [**Editing Integration/Repository Settings**](#editing-integrationrepository-settings)
  - [**Verifying Integration Settings**](#verifying-integration-settings)
  - [**Viewing Git Commits in Jira Data Center**](#viewing-git-commits-in-jiradata-center)
  - [More Integration Guides](#more-integration-guides)

<br>
<br>
<hr>
<br>
<br>

## Adding a Repository Hosted on Window Servers or Network Share

Obtain the network folder path to the project/collaboration folder.

The Connect wizard will continue without errors if the following conditions are met:

*   The network credentials accessing the git repository must be the same as the user running Jira.
*   The network path is not longer than 255 characters.
*   The user under which Jira is running should at least have **read** access to network path.

Add a new network share or Windows server hosted repository via the Connect to Git Repository wizard.

1. On your Jira dashboard menu, go to **Git** \> **Manage repositories**.

2\. Click **Connect to Git Repository** to open the Connect Wizard.

3\. Paste the network path in the **Repository Location** _field_.

4\. Configure the fetches option by clicking the **Advanced setup** label:

![](/wp-content/uploads/gij-win-share-repo-same-server-as-jira.png)

5\. Continue to the next step by following the screen instructions.

6\. Click **Finish** to complete this process.

Make sure that the network folder share name are correct and that the user has at least read access permissions to the network path.

The network/server share folder should now be connected with Jira.



## **Editing Integration/Repository Settings**

In the Git Repositories configuration page, edit the repository via **Actions** \> **Edit repository/integration settings**.

Under Repository Settings, set **_Enable Fetches_** option to  `Git repository hosted on the same server as Jira`.



## **Verifying Integration Settings**

Verify network folder share name by opening the shared folder properties.

For example:

![](https://bigbrassband.com/docimgs/win-share-folder-properties-dlg.png)

Make sure that the user has read access permissions to the network path.

For example:

![](https://bigbrassband.com/docimgs/win-share-access-rights-check.png)



## **Viewing Git Commits in Jira Data Center**

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.

<p>&nbsp;</p>

<br>
<br>

## More Integration Guides

[GitHub.com](/git-integration-for-jira-data-center/gitHub-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub Enterprise Server](/git-integration-for-jira-data-center/gitHub-Enterprise-Server-gij-self-managed)

[GitLab.com](/git-integration-for-jira-data-center/gitLab-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab CE/EE](/git-integration-for-jira-data-center/gitLab-com-CE-EE-gijsm-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Azure DevOps \| Visual Studio Team Services (VSTS)](/git-integration-for-jira-data-center/azure-DevOps-Visual-Studio-Team-Services-(VSTS)-gij-self-managed) (Git Integration for Data Center/Jira Server)

[Azure DevOps Server \| Team Foundation Services (TFS)](/git-integration-for-jira-data-center/azure-DevOps-Server-Team-Foundation-Services-(TFS)-gij-self-managed) (Git Integration for Jira Data Center/Server)

[AWS CodeCommit](/git-integration-for-jira-data-center/aws-codecommit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Gerrit](/git-integration-for-jira-data-center/gerrit-gij-self-managed) (Git Integration for Jira Data Center/Server)

**Windows Network \| Server Share** (this page)

[Tracked Folders](/git-integration-for-jira-data-center/tracked-Folders-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bitbucket Server](/git-integration-for-jira-data-center/Bitbucket-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bonobo](/git-integration-for-jira-data-center/bonobo-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Integration basics](/git-integration-for-jira-data-center/Integration-Basics-gij-self-managed) (Git Integration for Jira Data Center/Server)


