---

title: Windows Network | Server Share
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](https://bigbrassband.com/confluence/images/win-network-server-share-banner-logo.png)

**Integrate Windows Network/Server Share with Jira Data Center**



Quickly learn how to connect Windows Network or Server Share via Git Integration for Jira app.

* * *



## **Adding a Repository Hosted on Window Servers or Network Share**

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

![](https://bigbrassband.com/docimgs/win-share-repo-same-server-as-jira-144.png)

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

![](https://bigbrassband.com/docimgs/win-share-access-rights-check-144.png)



## **Viewing Git Commits in Jira Data Center**

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.

