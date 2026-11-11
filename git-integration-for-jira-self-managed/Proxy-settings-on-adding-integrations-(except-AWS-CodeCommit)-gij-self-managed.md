---

title: Proxy settings on adding integrations (except AWS CodeCommit)
description: Configure Jira HTTP and HTTPS proxy parameters for Git host integrations and check whether connections go through a proxy.
product: Git Integration for Jira Data Center
feature: Proxy and SSL
content_type: how-to
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira System Administrator]
version_required: all
status: GA
last_verified: 2023-10
llms_include: true
tags: [proxy, jvm parameters, 407 proxy authentication, hosts file]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "how-to-articles-gij-self-managed"
    nav_label: "Proxy settings on adding integrations (except AWS CodeCommit)"
    nav_order: 110
    nav_parent: "how-to-articles-gij-self-managed"
    page_type: "content"
---

<!-- how to -->

### Proxy settings for Jira

*   The client should specify **both** `http.proxyXXXX` and `https.proxyXXXX` parameters for Jira.

*   If the `Unable to tunnel through proxy. Proxy returns "HTTP/1.1 407 Proxy Authentication Required"` error occurs, then specify the options:

    `jdk.http.auth.tunneling.disabledSchemes=""`

    `jdk.http.auth.proxying.disabledSchemes=""`

> **Info:** For more information on setting up proxy settings for Jira, see <a href='https://confluence.atlassian.com/kb/how-to-configure-outbound-http-and-https-proxy-for-your-atlassian-application-834000120.html'>How to Configure Outbound HTTP and HTTPS Proxy for your Atlassian application.

&nbsp;

### How to check if your connection uses a proxy

If you are unsure whether the connection goes through a proxy or directly you may use the following trick. Add the following rows in the /etc/hosts file to fool the direct routing:

```java
5.255.255.77 testgerrit.bigbrassband.tk -- for Gerrit
5.255.255.77 app.vssps.visualstudio.com -- for Microsoft
5.255.255.77 dev.azure.com -- for Microsoft
...
etc
```

If your connection uses a proxy, you will be able to connect to the chosen integration because all connections will be executed on the remote proxy server. Otherwise, all connections will be executed on your local machine where integration hosts will have incorrect host resolving issue.

&nbsp;

### More How-to articles

[How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed/)

[Setting Project Permissions](/git-integration-for-jira-data-center/Setting-Project-Permissions-gij-self-managed)

[How to create a HAR file and send it to support for analysis](/git-integration-for-jira-data-center/how-to-create-a-har-file-and-send-it-to-support-for-analysis-gij-self-managed/)

[Working with Custom API Path](/git-integration-for-jira-data-center/Working-with-Custom-API-Path-gij-self-managed)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

[Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

[Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/Require-Personal-Access-Tokens-for-user-actions-(create-branch-pull-request)-gij-self-managed)

[Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/Ways-to-Index-Git-Data-to-Jira-Issues-gij-self-managed)

**Proxy settings on adding integrations (except AWS CodeCommit)** (this page)

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

