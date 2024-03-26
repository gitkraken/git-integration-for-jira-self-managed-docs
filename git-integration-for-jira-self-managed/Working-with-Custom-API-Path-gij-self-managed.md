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
  - [1. Lists all repositories (default)](#GH1)
  - [2. Display all repositories from \<username\>](#GH2)
  - [3. Displays starred repositories](#GH3)
  - [4. List all repositories for the specified organization](#GH4)
- [GitLab.com and GitLab CE|EE examples](#gitlabcom-and-gitlab-ceee-examples)
  - [1. Lists all projects (default)](#GL1)
  - [2. Display all projects from \<user\_id\>](#GL2)
  - [3. Displays starred projects](#GL3)
  - [4. Limit to owned projects](#GL4)
  - [5. List projects from within a group](#GL5)
  - [6. List projects from the specified subgroup](#GL6)
- [More how-to articles](#more-how-to-articles)

&nbsp;
* * *
&nbsp;

### Accessible locations

*   Add new integration Wizard ➜ Connection screen ➜ _Advanced_ ➜ **Custom API Path**.

    For example:

    ![](/wp-content/uploads/gij-gitserver-github-custom-api-path-01.png)

&nbsp;

*   Manage repositories page ➜ ![](/wp-content/uploads/actions-icon.png) Actions ➜ Edit integration connection settings ➜ **Custom API Path**.

    ![](/wp-content/uploads/gij-gitserver-actions-int-conn-cfg-custom-apipath.png)

&nbsp;

<span id='githubcom-and-github-enterprise-examples'></span> <!-- set anchor -->
<img src='/wp-content/uploads/github-mobile-dark.png' width=40 height=40 style='margin-bottom:10px;display:block;' />

### GitHub\.com and GitHub Enterprise examples

<p id='GH1'><b>1. Lists all repositories (default)</b></p>

`/user/repos`

Gets a list of repositories by the authenticated user. This is the same as when no API path is specified.

<p id='GH2'><b>2. Display all repositories from \<username\></b></p>

`/users/<username>/repos`

Gets a list of public repositories for the specified user, **\<username\>**.

**For example:** `/users/johnsmith/repos`

<p id='GH3'><b>3. Displays starred repositories</b></p>

`/user/starred`

Gets a list of repositories by the authenticated user. This is the same as when no API path is specified.

`/users/<username>/starred`

Gets the list of starred public/private repositories for the specified user, **\<username\>**.

**For example:** `/users/johnsmith/starred`

<p id='GH4'><b>4. List all repositories for the specified organization</b></p>

`/orgs/<org>/repos`

Gets a list of repositories for the specified org, **\<org\>**. __GitKraken__

**For instance:**

`/orgs/GitKraken/repos`

This will filter for repositories only within the org: `BigBrassBand`. This works for GitHub integrations.

&nbsp;

<span id='gitlabcom-and-gitlab-ceee-examples'></span> <!-- set anchor -->
<img src='/wp-content/uploads/gij-gitlab-mobile.png' width=40 height=40 style='margin-bottom:10px;display:block;' />

### GitLab\.com and GitLab CE\|EE examples

<p id='GL1'><b>1. Lists all projects (default)</b></p>

`/api/v4/projects?membership=true`

Gets a list of projects. This is the same as when no API path is specified.

<p id='GL2'><b>2. Display all projects from &lt;user_id&gt;</b></p>

`/api/v4/users/<user_id>/projects`

Gets a list of projects for the specified user, **\<user\_id\>**.  _**johnsmith**_

<p id='GL3'><b>3. Displays starred projects</b></p>

`/api/v4/projects?starred=true`

Returns GitLab projects that have been starred by the connecting GitLab user.

<p id='GL4'><b>4. Limit to owned projects</b></p>

`/api/v4/projects?owned=true`

The current user will be limited to the projects it's explicitly owned.

<p id='GL5'><b>5. List projects from within a group</b></p>

`/api/v4/groups/5245789/projects<br>/api/v4/groups/BigBrassBand/projects`

Returns the list of repositories within a GitLab group (or GitLab subgroup).

In the above examples, you can use the **Group id** or your **Group** **name** as query parameter.

<p id='GL6'><b>6. List projects from the specified subgroup</b></p>

`/api/v4/groups/5245789/projects?include_subgroups=true`
`/api/v4/groups/GitKraken/projects?include_subgroups=true`

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

While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

&nbsp;

### More how-to articles

[How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed/)

[Setting Project Permissions](/git-integration-for-jira-data-center/Setting-Project-Permissions-gij-self-managed)

[How to create a HAR file and send it to support for analysis](/git-integration-for-jira-data-center/how-to-create-a-har-file-and-send-it-to-support-for-analysis-gij-self-managed/)

**Working with Custom API Path** (this page)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

[Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

[Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/Require-Personal-Access-Tokens-for-user-actions-(create-branch-pull-request)-gij-self-managed)

[Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/Ways-to-Index-Git-Data-to-Jira-Issues-gij-self-managed)

[Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/Proxy-settings-on-adding-integrations-(except-AWS-CodeCommit)-gij-self-managed)

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

<div style='border-top: 1px solid #456; width: 40%; padding-bottom: 12px'></div>
<div style='font-size: 12px;'>
    <sup>1</sup> <i>Logo owned by <a href='https://gitlab.com/'>GitLab Inc</a> used under <a href='https://creativecommons.org/licenses/by-nc-sa/4.0/'>license</a>.
    <p>&nbsp;&nbsp;All product names, logos, and brands are property of their respective owners.</p></i>
</div>

