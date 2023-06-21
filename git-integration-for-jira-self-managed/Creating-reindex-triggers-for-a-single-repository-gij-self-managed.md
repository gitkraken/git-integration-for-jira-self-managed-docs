---

title: Creating reindex triggers for a single repository
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

To create a webhook that triggers the reindex of a single repository, the following requirements are required::

*   The `git_http_url` matches the **Repository Origin** URL from the Jira git configuration page (Jira dashboard menu Git ➜ Manage repositories ➜Actions ➜ **Edit integration settings**).

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b> The **Content-Type** request header is set to `application/json`.

*   Use the webhook secret key from the git configuration page ➜ **Webhooks**.

<br>

The webhook is a POST request with the following JSON body:

```json
{
  "repository": { "git_http_url": "https://gitlab.com/bbb-dev/bbb-testrepo.git" 
  }
}
```

<br><br>

**For example:**

![](/wp-content/uploads/gij-webhook-reindex-post-api-json.png)

<br><br>

**Result:**

The repository is placed in the indexing queue via the git repositories configuration page (_Jira dashboard menu Git ➜ **Manage repositories**_).

&nbsp;

### More related articles about webhooks setup

**Creating reindex triggers for a single repository** (this page)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/adding-webhooks-for-gerrit-gij-self-managed)

