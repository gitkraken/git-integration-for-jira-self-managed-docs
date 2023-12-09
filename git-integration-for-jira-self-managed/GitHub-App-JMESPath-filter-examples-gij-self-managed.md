---

title: GitHub App JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/gij-github-mobile-logo-dark.png)

&nbsp;

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.8+</b> We have implemented JMESPath filters supporting GitHub Application integrations.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Do note that the declared string format is case-sensitive.
    </div>
    </div>
</div>

&nbsp;

This filter will allow users to connect only those repositories from a GitHub App integration that matches the JMESPath expression.

GitHub applications have two type of scopes:

*   **Selected repositories** &nbsp;&ndash;&nbsp; this type works in the same way JMESPath filter is used in standard GitHub integrations:

    *   the user selects the particular repositories and after that, this set of connected repositories is not changed during reindex of the integration.

*   **All repositories** &nbsp;&ndash;&nbsp; this type works in another way, where, the set of repositories is changing dynamically as the scope includes **all** repositories:

    *   when new repositories appear in the organization, they are added to the scope. 

    *   when some repositories are deleted from the organization, they are removed from the scope.

So if the user selects the **All repositories** scope, it would be more convenient to select repositories using JMESPath. This is in order for the new repositories appearing in the organization to be filtered by JMESPath automatically.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        JMESPath expressions can have the same format as GitHub integrations connected using a PAT.
    </div>
    </div>
</div>

&nbsp;

GitHub Apps have different JMESPath format in comparison with previous GitHub integrations:

*   it must start with `repositories[] |` and then,

*   it should be followed by any valid JMESPath from standard GitHub integration.

&nbsp;

### 1\. Starts with

`repositories[] | [?starts_with(name, 'repo-prefix')]`

This is a filter based on the text in the repository name. It lists repositories with the names that start with the specified word. Do note that the declared string format is case-sensitive.

&nbsp;

### 2\. Contains (include)

`repositories[] | [?contains(name, 'substring')]`

Lists repositories with the names that contain the specified word.

&nbsp;

### 3\. Contains (exclude)

`repositories[] | [?(!contains(name, 'search-phrase'))]`

Lists repositories with the names that do not contain the specified word.

&nbsp;

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <code>!condition</code> must be wrapped in a parenthesis so it won’t invert the whole expression.
    </div>
    </div>
</div>

&nbsp;

### 4\. Specific (exact)

`repositories[] | [?name == 'exact-repo-name']`

Lists repositories with the exact specified name.

&nbsp;
* * *
&nbsp;

### More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

**GitHub App JMESPath filter examples** (this page)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

