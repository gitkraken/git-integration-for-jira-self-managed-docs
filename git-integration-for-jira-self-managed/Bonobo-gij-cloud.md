---

title: Bonobo
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.com/confluence/images/bonobo-banner-logo.png)

**Integrate Bonobo with Jira Data Center**



Quickly learn how to connect Bonobo git repositories via Git Integration for Jira app.

**What's on this page:**



* * *

## **Single Repository**

Obtain the repository URL from the Bonobo repository project page.

1.  On your Jira dashboard menu, go to **Git** > **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from Bonobo web portal in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Data Center.



## **Setting Up Weblinks**

This feature is optional.

Configure web links from either of the following locations:

*   **Advanced setup** in Connect Wizard
*   **Git** > **Manage repositories** > **Edit repository/integration** settings.

Select the Bonobo git host from the **Web Link** dropdown list.

Set the variables to the actual URL settings of the git host. In this case, replace **<host>** and **<project>** with actual path names.

Save the changes.



## **Viewing Git Commits in Jira Data Center**

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.

