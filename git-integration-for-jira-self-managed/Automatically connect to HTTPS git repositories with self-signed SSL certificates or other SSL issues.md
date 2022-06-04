---

title: Automatically connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Perform auto-connect integration with HTTPS git repositories that have self-signed SSL certificates or other SSL issues. For this guide, we will use GitLab as an example:

1.  On your Jira dashboard, go to menu Git ➜ **Manage repositories**.

2.  On the Add new integration panel, click **GitLab**.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930397370/gitserver-auto-connect-panel-gitlab-sel(c).png?version=1&modificationDate=1630642838459&cacheVersion=1&api=v2)
3.  For External service, select **GitLab Server (CE/EE) v4**. Support for v3 is deprecated.

4.  Enter the remote URL of the private git server.

5.  Enter Personal access token for this server.

6.  Click **Connect** to continue. If there is an indication of an SSL error, the following screen is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397370/gitserver-gitlab-server-bad-ssl-example(c).png?version=1&modificationDate=1630642838950&cacheVersion=1&api=v2&width=646&height=428)
7.  Click **Ignore certificate errors and continue connection**. This will ignore SSL verification if it's self-signed or expired.

8.  Import the detected repositories and then click **Finish** to complete the setup.

* * *

[Previous: Self-signed HTTPS connections](/git-integration-for-jira-self-managed/self-signed-https-integration/)

[Next: Manually connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues](/git-integration-for-jira-self-managed/manually-connect-to-https-git-repositories-with-self-signed-ssl-certificates-or-other-ssl-issues/)

