---

title: Pull request timeline - TIJ DC
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This feature requires Git Integration for Jira DC app installed to be able to see pull request data in Team Insights for Jira.
    </div>
    </div>
</div>

This feature supports pull/merge request (PR/MR) event history and it projects PR/MR reindex data to Team Insights for Jira (TIJ). The Git Integration for Jira app should be installed to be able to see more details in TIJ tasks and backlog view.

For now, only GitHub and GitLab git services are currently supported.

&nbsp;

### What happens if these extended permissions are not set?

Errors on the reindex will occur. The git host will generate the logs detailing the cause of the error.

Example GitHub generated error log:

```json
{
  "locations":[{"line":1,"column":1615}],
  "type":"INSUFFICIENT_SCOPES",
  "message":"Your token has not been granted the required scopes to execute this query. The 'email' field requires one of the following scopes: ['user:email', 'read:user'], but your token has only been granted the: ['admin:org_hook', 'admin:public_key', 'admin:repo_hook', 'read:org', 'repo'] scopes. Please modify your token's scopes at: https://github.com/settings/tokens."
}
```

&nbsp;

### Permission requirements for project access token

It is important that Git administrators must set the minimum permission requirements in an organization/group as follows:

#### GitHub org

| Permissions | Description |
|:------------|:------------|
| admin:org ➜ **read:org** | Under **admin:org** scope group, enable the **read:org** setting. This grants permission to read org and team membership as well as read org projects. This is required to read information about users with the organization type.<br><img src='/wp-content/uploads/tij-gitcloud-pull-req-timeline-reindex-github-org-setting.png' style='margin:15px auto 0px auto;max-width:100%;display:block;' /> |
| user ➜ **user:email** | Under **user** scope group, enable the **user:email** setting. This grants read-only access to user email addresses. This is required to read the user's email address information which is then used to match with users from Jira. |
| user ➜ **read:user** | Optional. This grants read access to all user profile data. |
| **_read:discussion_** | Optional. This grants read access to team discussions. |

&nbsp;

#### GitLab group

| Permissions | Description |
|:------------|:------------|
| **_Role_** | At least Reporter role. |
| **_Scope_** | At least read_api scope. |

&nbsp;

### Which permission scopes should be set for GitHub App integration?

Only these two scopes are required for GitHub App integration:

*   **read:org** – Read org and team membership, read org projects, and 

*   **user:email** – Access user email addresses (read-only).

