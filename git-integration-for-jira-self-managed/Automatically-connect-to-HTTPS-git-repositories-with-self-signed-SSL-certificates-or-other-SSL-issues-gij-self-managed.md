---

title: Automatically connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Perform auto-connect integration with HTTPS git repositories that have self-signed SSL certificates or other SSL issues. For this guide, we will use GitLab as an example:

1.  On your Jira dashboard, go to menu Git ➜ **Manage repositories**.

2.  On the Add new integration panel, click **GitLab**.

    ![](/wp-content/uploads/gij-gitserver-auto-connect-panel-gitlab-sel-c.png)

3.  For External service, select **GitLab Server (CE/EE) v4**. Support for v3 is deprecated.

4.  Enter the remote URL of the private git server.

5.  Enter Personal access token for this server.

6.  Click **Connect** to continue. If there is an indication of an SSL error, the following screen is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitlab-server-bad-ssl-example-c.png)

7.  Click **Ignore certificate errors and continue connection**. This will ignore SSL verification if it's self-signed or expired.

8.  Import the detected repositories and then click **Finish** to complete the setup.

<br>

## More related topics about self-signed HTTPS integration

[Self-signed HTTPS integration](/git-integration-for-jira-data-center/self-signed-https-integration-gij-self-managed)

**Automatically connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues** (this page)

[Manually connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues](/git-integration-for-jira-data-center/manually-connect-to-HTTPS-git-repositories-with-self-signed-SSL-certificates-or-other-SSL-issues-gij-self-managed)

