---

title: Connecting to a single git repository (HTTPS | SSH)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/2044035207/gitlab-repository-home.png?version=1&modificationDate=1640790600104&cacheVersion=1&api=v2)

This process requires an existing git host repository. Obtain the **HTTPS** or **SSH** git clone URL from the repository home of your git host service.

To connect a git repository to Jira via the Git Integration for Jira app:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2044035207/gitserver-gitmgr-connect-repo-sel.png?version=1&modificationDate=1640790600110&cacheVersion=1&api=v2&width=680&height=402)

1.  Go to dashboard menu Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** or click the **Git** icon on the Add new integration panel. The Connect Wizard is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2044035207/gitserver-connect-wizard-01(c).png?version=1&modificationDate=1640790600121&cacheVersion=1&api=v2&width=646&height=502)
    *   Enter the repository clone URL on the provided box. Initially, the repository URL can be obtained from the repository's project page.

    *   If you want to control the repository connection options, click the **Advanced setup** label.

3.  Click **Next** if you want to skip advanced setup and proceed with the standard setup. The **Authentication** screen is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2044035207/gitserver-connect-wizard-02a.png?version=1&modificationDate=1640790600123&cacheVersion=1&api=v2&width=646&height=428)
    *   For HTTPS/HTTP connections, enter login credentials. If two-factor authentication is enabled for your git host, enter the personal access token as the password instead.

    *   If your repository clone URL is an SSH connection, upload or paste the private key in the respective input box and enter other required fields.

4.  Click **Next**. The Settings screen is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2044035207/gitserver-connect-wizard-03a.png?version=1&modificationDate=1640790600125&cacheVersion=1&api=v2&width=646&height=391)
    *   Change settings for [Smart Commits](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/1923029046) and [Repository Browser](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/1923029214) as required or leave the default settings as it is.

    *   For **Project Permissions** settings, [see this article](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/1923028500) for more information.

5.  Click **Finish** to complete this setup.


The repository is now connected for use with Jira.

