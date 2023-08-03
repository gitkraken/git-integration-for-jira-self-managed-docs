---

title: Webhooks GitHub Organization Support
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The GitHub Organization webhooks is now supported.  Rather than creating a webhook for each repository manually, configure the webhook at the GitHub Organization level to automatically register webhook for each repository.

![](/wp-content/uploads/gij-gitserver-github-org-webhooks-cfg.png)

To configure GitHub organization webhook:

1.  Login to your GitHub account and go to your GitHub Organization.

2.  Go to **Settings**.

3.  On the sidebar under _Code, planning, and automation_, go to **Webhooks**.

    *   On the Webhooks page, click **Add webhook**.

4.  Paste the webhook URL into the _**Payload URL**_ field. (The webhook URL is acquired from the Git Integration for Jira app [webhook configuration page](/git-integrationn-for-jira-data-center/webhooks-gij-self-managed).)

5.  <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b>  For the <b>Content type</b>, choose `applications/json`.

6.  Enter the **Secret key** on the _**Secret**_ field.

7.  Set the webhook trigger to **Just the Push event**.

8.  Click **Add webhook** to complete this setup.

&nbsp;

### More related articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

**Webhooks GitHub Organization support** (this page)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/adding-webhooks-for-gerrit-gij-self-managed)

