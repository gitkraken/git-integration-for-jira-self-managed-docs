---

title: Working with Custom API Path
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The Custom API Path is a relative path that starts with "/".  The maximum allowed length is 2000 characters. The integration will use the relative REST API path to retrieve the list of tracked repositories.

The Custom API Path is called in the integration setup, settings changes, on a regular scheduled reindex and for a manual reindex.

**What's on this page:**
- [Accessible locations](#accessible-locations)
- [GitHub.com and GitHub Enterprise examples](#githubcom-and-github-enterprise-examples)
- [GitLab.com and GitLab CE|EE examples](#gitlabcom-and-gitlab-ceee-examples)
- [More how-to articles](#more-how-to-articles)

* * *

## Accessible locations

*   Add new integration Wizard ➜ Connection screen ➜ _Advanced_ ➜ **Custom API Path**.

    For example:
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/135331922/gitserver-auto-connect-github-example.png?version=2&modificationDate=1642507945521&cacheVersion=1&api=v2&width=680&height=455)

<br>

*   Manage repositories page ➜ <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ Edit integration connection settings ➜ **Custom API Path**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/135331922/gitserver-actions-int-conn-cfg-custom-apipath.png?version=1&modificationDate=1642507945571&cacheVersion=1&api=v2&width=680&height=612)

<br>

## GitHub.com and GitHub Enterprise examples

1.  **Lists all repositories (default)**

    ```java
    /user/repos
    ```

    Gets a list of repositories by the authenticated user. This is the same as when no API path is specified.

2.  **Display all repositories from \<username\>**

    ```java
    /users/<username>/repos
    ```

    Gets a list of public repositories for the specified user, **\<username\>**.

    **For example:** `/users/johnsmith/repos`

3.  **Displays starred repositories**

    ```java
    /user/starred
    ```

    Gets a list of repositories by the authenticated user. This is the same as when no API path is specified.

    ```java
    /users/<username>/starred
    ```

    Gets the list of starred public/private repositories for the specified user, **\<username\>**.

    **For example:** `/users/johnsmith/starred`

5.  **List all repositories for the specified organization**

    ```java
    /orgs/<org>/repos
    ```

    Gets a list of repositories for the specified org, **
    \<org\>**. _BigBrassBand_

    **For instance:**

    ```java
    /orgs/BigBrassBand/repos
    ```

    This will filter for repositories only within the org: `BigBrassBand`. This works for GitHub integrations.

<br>

## GitLab.com and GitLab CE|EE examples

1.  **Lists all projects (default)**

    ```java
    /api/v4/projects?membership=true
    ```

    Gets a list of projects. This is the same as when no API path is specified.

2.  **Display all projects from \<user\_id\>**

    ```java
    /api/v4/users/<user_id>/projects
    ```

    Gets a list of projects for the specified user, **\<user\_id\>**. _johnsmith_

3.  **Displays starred projects**

    ```java
    /api/v4/projects?starred=true
    ```

    Returns GitLab projects that have been starred by the connecting GitLab user.

4.  **Limit to owned projects**

    ```java
    /api/v4/projects?owned=true
    ```

    The current user will be limited to the projects it's explicitly owned.

5.  **List projects from within a Group**

    ```java
    /api/v4/groups/5245789/projects<br>/api/v4/groups/BigBrassBand/projects
    ```

    Returns the list of repositories within a GitLab Group (or GitLab Subgroup).
    
    In the above examples, you can use the **Group id** or your **Group** **name** as query parameter.

6.  **List projects from the specified sub-group**

    ```java
    /api/v4/groups/5245789/projects?include_subgroups=true
    /api/v4/groups/BigBrassBand/projects?include_subgroups=true
    ```

    In the above examples, the `?include_subgroups=true` API extension will return a recursive list of repositories within a nested GitLab Group (or GitLab Subgroup) where the #, `5245789`, is the **Group id**; and `BigBrassBand` is the **Group name**.


For more information on GitLab custom API paths, see **GitLab API**.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>GitLab version API support:</b><br>
        Gitlab v9.5 and above -- only API v4<br>
        Gitlab v9.0 to v9.4.x -- API v3 and API v4 (<i>support for API v3 is deprecated</i>)
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Remember</b><br>
        The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible. For more information, see <a href='/git-integration-for-jira-self-managed/working-with-jmespath-filters-gij-self-managed/'>Working with JMESPath filters</a>.
    </div>
    </div>
</div>
<br>

While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

## More how-to articles

*   [Creating Personal Access Tokens](/git-integration-for-jira-self-managed/creating-personal-access-tokens-gij-self-managed/)
*   [Working with JMESPath Filters](/git-integration-for-jira-self-managed/working-with-jmespath-filters-gij-self-managed/)
*   [Working with Custom API Path](/git-integration-for-jira-self-managed/working-with-custom-api-path-gij-self-managed/)
*   [Setting Project Permissions](/git-integration-for-jira-self-managed/setting-project-permissions-gij-self-managed/)
*   [Configure Source Code Diff Viewing](/git-integration-for-jira-self-managed/configure-source-code-diff-viewing-gij-self-managed/)
*   [Configure Repository Browser](/git-integration-for-jira-self-managed/configure-repository-browser-gij-self-managed/)
*   [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed/)
*   [Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-self-managed/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed/)
*   [How to get a quote?](/git-integration-for-jira-self-managed/how-to-get-a-quote-gij-self-managed/)
*   [Ways to Index Git Data to Jira Issues](/git-integration-for-jira-self-managed/ways-to-index-git-data-to-jira-gij-self-managed/)
*   [Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-self-managed/proxy-settings-on-adding-integrations-except-aws-codecommit-gij-self-managed/)

<br>
<hr>

_1 Logo owned by_ [_GitLab Inc_](https://gitlab.com/) _used under_ [_license_](https://creativecommons.org/licenses/by-nc-sa/4.0/)

