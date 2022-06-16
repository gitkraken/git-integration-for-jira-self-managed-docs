---

title: Self-signed HTTPS integration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
**INTRODUCED IN VERSION 2.11.2**

Self-signed certificates are common in HTTPS Git repositories that are hosted privately. Even for an administrator, it's not easy to set the HTTP `sslVerify` to connect to this repository.

As of **v2.11.2+** of the Git Integration app, the Jira administrator now has the option to disable `sslVerify` for specific repositories while inside Jira.

This feature is available in [Connect to Git Repository](/git-integration-for-jira-self-managed/using-the-connect-repository-wizard/) wizard and [Add new integration wizard](/git-integration-for-jira-self-managed/using-the-add-new-integration-wizard/) for GitHub and GitLab.

