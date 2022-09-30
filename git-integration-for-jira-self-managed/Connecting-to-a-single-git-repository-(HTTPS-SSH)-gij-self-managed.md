---

title: Connecting to a single git repository (HTTPS/SSH) (Integration basics)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](wp-content/uploads/gij-gitlab-repository-home.png)

This process requires an existing git host repository. Obtain the **HTTPS** or **SSH** git clone URL from the repository home of your git host service.

To connect a git repository to Jira via the Git Integration for Jira app:

![](/wp-content/uploads/gij-gitserver-gitmgr-connect-repo-sel.png)

1.  Go to dashboard menu Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** or click the **Git** icon on the Add new integration panel. The Connect Wizard is displayed.

    ![](/wp-content/uploads/gij-gitserver-connect-wizard-01-c.png)

    *   Enter the repository clone URL on the provided box. Initially, the repository URL can be obtained from the repository's project page.

    *   If you want to control the repository connection options, click the **Advanced setup** label.

3.  Click **Next** if you want to skip advanced setup and proceed with the standard setup. The **Authentication** screen is displayed.

    ![](/wp-content/uploads/gij-gitserver-connect-wizard-02a.png)
    
    *   For HTTPS/HTTP connections, enter login credentials. If two-factor authentication is enabled for your git host, enter the personal access token as the password instead.

    *   If your repository clone URL is an SSH connection, upload or paste the private key in the respective input box and enter other required fields.

4.  Click **Next**. The Settings screen is displayed.

    ![](/wp-content/uploads/gij-gitserver-connect-wizard-03a.png)
    
    *   Change settings for [Smart Commits](/git-integration-for-jira-data-center/smart-commits-docs-gij-self-managed) and [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed) as required or leave the default settings as it is.

    *   For **Project Permissions** settings, [see this article](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed) for more information.

5.  Click **Finish** to complete this setup.


The repository is now connected for use with Jira.

## More related articles on integration basics

[Connecting to a git host account via Add new integration panel](/git-integration-for-jira-data-center/connecting-to-a-git-host-account-via-Add-new-integration-panel-gij-self-managed)

**Connecting to a single git repository (HTTPS | SSH)** (this page)

[Setting up web links](/git-integration-for-jira-data-center-gij-self-managed/setting-up-web-links-gij-self-managed)

[Link git commits to Jira issues (Basics)](/git-integration-for-jira-data-center/Link-git-commits-to-Jira-issues-(Basics)-gij-self-managed)

[Using smart commits](/git-integration-for-jira-data-center/using-smart-commits-gij-self-managed)

[Using the Repository Browser](/git-integration-for-jira-data-center/using-the-repository-browser-gij-self-managed)

[Creating branches and pull | merge requests (Basics)](/git-integration-for-jira-data-center/Creating-branches-and-pull-merge-requests-(Basics)-gij-self-managed)

