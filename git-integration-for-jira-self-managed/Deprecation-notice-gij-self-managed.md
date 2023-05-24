---

title: Deprecation notice
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

| Feature | Date | Details of ending support, removal or obsolescence |
| :--- | :--- | :--- |
| **Integrations feature settings: Limit commits** | After 1 January 2021 | The 'Limit commits...' setting is deprecated and will be removed. Thenceforth, all commits will be limited by project permissions.<br><br>![](/wp-content/uploads/gij-limit-commit-deprecation-notice.png) |
| **Personal access tokens** | Dependent on which Git service | Some Git services such as GitLab and GitHub are enforcing authentication access for users to use personal access tokens in accessing git resources and services. |
| **`${username}`** | Effective 29 April 2019 | The `${username}` is used when logging into Jira and in the branch name template to generate a default name for newly-created branches. This template variable is deprecated as Atlassian is no longer making usernames available. |
| **Ignore unmatching webhooks** | Starting v3.8+ | We will no longer reindex all repositories by default when a webhook arrives without a matching repository. There will be a setting in the Webhooks setting page where the previous functionality can be restored.<br><br>The advanced options provide a couple of settings for webhook indexing performance improvements.<br><br>![](/wp-content/uploads/gij-gitserver-webhooks-ignore-dups-and-min-ridx-adv.png) |
| **StartReindexGitRepositories** | Starting v4.16+ | This action is deprecated since it is not being used by GIJ starting v4.16 and later.<br><br>For example: <ul><li>http://localhost/secure/StartReindexGitRepositories.jspa</li><li>http://localhost/secure/ReindexGitRepositories!progress.jspa</li></ul><br>These actions will be removed from GIJ Server/DC product in 12 months. |
| Reindex POST API<br>**/jira/rest/gitplugin/1.0/index** | Starting v4.17+ | **Contet-type: multipart/form-data** is also deprecated.for Reindex POST API.<br><br>The v2.0 API with JSON body is more improved and users are advised to update to v4.17+ for better security. |
| _(more to come)_ |     |     |

