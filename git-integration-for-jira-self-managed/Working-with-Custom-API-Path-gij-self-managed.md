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
- [GitHub.com and GitHub Enterprise examples](#github-com-and-github-enterprise-examples)
  - [1\. Lists all repositories (default)](#1-lists-all-repositories-default)
  - [2\. Display all repositories from \<username\>](#2-display-all-repositories-from-username)
  - [3\. Displays starred repositories](#3-displays-starred-repositories)
  - [4\. List all repositories for the specified organization](#4-list-all-repositories-for-the-specified-organization)
- [GitLab.com and GitLab CE|EE examples](#gitlab-com-and-gitlab-ceee-examples)
  - [1\. Lists all projects (default)](#1-lists-all-projects-default)
  - [2\. Display all projects from \<user\_id\>](#2-display-all-projects-from-user_id)
  - [3\. Displays starred projects](#3-displays-starred-projects)
  - [4\. Limit to owned projects](#4-limit-to-owned-projects)
  - [5\. List projects from within a group](#5-list-projects-from-within-a-group)
  - [6\. List projects from the specified sub-group](#6-list-projects-from-the-specified-subgroup)
- [More how-to articles](#more-how-to-articles)

<br>
<br>
<hr>
<br>
<br>

## Accessible locations

*   Add new integration Wizard ➜ Connection screen ➜ _Advanced_ ➜ **Custom API Path**.

    For example:
    
    ![](/wp-content/uploads/gij-gitserver-github-custom-api-path-01.png)

<br>

*   Manage repositories page ➜ <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Edit integration connection settings ➜ **Custom API Path**.

    ![](/wp-content/uploads/gij-gitserver-actions-int-conn-cfg-custom-apipath.png)

<br>

<img src='/wp-content/uploads/github-mobile-dark.png' width=40 height=40 style='margin-bottom:10px;display:block;' />

## GitHub.com and GitHub Enterprise examples

### 1\. Lists all repositories (default)

    `/user/repos`

    Gets a list of repositories by the authenticated user. This is the same as when no API path is specified.

### 2\. Display all repositories from \<username\>

    `/users/<username>/repos`

    Gets a list of public repositories for the specified user, **\<username\>**.

    **For example:** `/users/johnsmith/repos`

### 3\. Displays starred repositories

    `/user/starred`

    Gets a list of repositories by the authenticated user. This is the same as when no API path is specified.

    `/users/<username>/starred`

    Gets the list of starred public/private repositories for the specified user, **\<username\>**.

    **For example:** `/users/johnsmith/starred`

### 4\. List all repositories for the specified organization

    `/orgs/<org>/repos`

    Gets a list of repositories for the specified org, **\<org\>**. __GitKraken__

    **For instance:**

    `/orgs/GitKraken/repos`

    This will filter for repositories only within the org: `BigBrassBand`. This works for GitHub integrations.

<br>

<img src='/wp-content/uploads/gij-gitlab-mobile.png' width=40 height=40 style='margin-bottom:10px;display:block;' />

## GitLab.com and GitLab CE|EE examples

### 1\. Lists all projects (default)

    `/api/v4/projects?membership=true`

    Gets a list of projects. This is the same as when no API path is specified.

### 2\. Display all projects from \<user\_id\>

    `/api/v4/users/<user_id>/projects`

    Gets a list of projects for the specified user, **\<user\_id\>**.  __johnsmith__

### 3\. Displays starred projects

    `/api/v4/projects?starred=true`

    Returns GitLab projects that have been starred by the connecting GitLab user.

### 4\. Limit to owned projects

    `/api/v4/projects?owned=true`

    The current user will be limited to the projects it's explicitly owned.

### 5\. List projects from within a group

    `/api/v4/groups/5245789/projects<br>/api/v4/groups/BigBrassBand/projects`

    Returns the list of repositories within a GitLab group (or GitLab subgroup).
    
    In the above examples, you can use the **Group id** or your **Group** **name** as query parameter.

### 6\. List projects from the specified subgroup

    `/api/v4/groups/5245789/projects?include_subgroups=true
    /api/v4/groups/GitKraken/projects?include_subgroups=true
    `

    In the above examples, the `?include_subgroups=true` API extension will return a recursive list of repositories within a nested GitLab Group (or GitLab Subgroup) where the #, `5245789`, is the **Group id**; and `GitKraken` is the **Group name**.


For more information on GitLab custom API paths, see <a href='https://docs.gitlab.com/ee/api/' target='_blank'><b>GitLab API</b></a>.

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
        The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible. For more information, see <a href='/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed'>Working with JMESPath filters</a>.
    </div>
    </div>
</div>
<br>

While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

## More how-to articles

*   [Creating Personal Access Tokens](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed)

*   [Working with JMESPath Filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed)

*   [Working with Custom API Path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed)

*   [Setting Project Permissions](/git-integration-for-jira-data-center/setting-project-permissions-gij-self-managed)

*   [Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

*   [Configure Repository Browser](/git-integration-for-jira-data-center/configure-repository-browser-gij-self-managed)

*   [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed)

*   [Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

*   [How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed)

*   [Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/ways-to-index-git-data-to-jira-gij-self-managed)

*   [Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/proxy-settings-on-adding-integrations-except-aws-codecommit-gij-self-managed)

<p>&nbsp;</p>

<br>
<br>
<br>
<br>

<div style='border-top: 1px solid #456; width: 40%; padding-bottom: 12px'></div>
<div style='font-size: 12px;'>
    <sup>1</sup> <i>Logo owned by <a href='https://gitlab.com/'>GitLab Inc</a> used under <a href='https://creativecommons.org/licenses/by-nc-sa/4.0/'>license</a>.
    <p>&nbsp;&nbsp;All product names, logos, and brands are property of their respective owners.</p></i>
</div>

