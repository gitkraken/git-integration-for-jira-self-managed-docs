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
| **Ignore unmatching webhooks** | 14 September 2021 | Starting v3.8+<br>We will no longer reindex all repositories by default when a webhook arrives without a matching repository. There will be a setting in the Webhooks setting page where the previous functionality can be restored.<br><br>The advanced options provide a couple of settings for webhook indexing performance improvements.<br><br>![](/wp-content/uploads/gij-gitserver-webhooks-ignore-dups-and-min-ridx-adv.png) |
| **StartReindexGitRepositories** | 12 April 2023 | Starting v4.16+<br>This action is deprecated since it is not being used anymore by GIJ.<br><br>For example: <ul><li>http://localhost/secure/StartReindexGitRepositories.jspa</li><li>http://localhost/secure/ReindexGitRepositories!progress.jspa</li></ul><br>These actions will be removed from GIJ Server/DC product in 12 months. |
| Reindex POST API<br>**/jira/rest/gitplugin/1.0/index** | 04 May 2023 | Starting v4.17+<br>**Contet-type: multipart/form-data** is also deprecated.for Reindex POST API.<br><br>The v2.0 API with JSON body is more improved and users are advised to update to v4.17+ for better security. |
| **GitLab legacy** | 06 June 2023<br>March 2024 | Starting v4.19+<br>We will be dropping support for GitLab legacy integrations.<br><br>The removal of legacy routes in the recent Gitlab update is breaking links from our apps -- as the URL structure has changed. More details regarding the change [here](https://docs.gitlab.com/ee/update/removals.html#legacy-routes-removed).<br><br><div class="bbb-callout bbb--alert"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">GitLab Legacy integrations support feature will be fully dropped from our apps by March 2024. Please upgrade your GitLab server, disconnect the legacy integration and connect a new GitLab EE integration.</div></div></div> |
| **Java 8** | Q2 2024 | Starting Git Integration for Jira app v5.0, it will no longer support Java 8. We recommend to upgrade to newer versions of Java especially for security reasons. |
| _(more to come)_ |     |     |

