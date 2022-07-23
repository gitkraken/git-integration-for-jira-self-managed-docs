---

title: Branch and pull request settings (formerly Git Integration Options)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed/'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>
<br>

This setting affects git branches creation default names and toggles for git pull/merge request options for the Jira issue.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207828745/gitserver-gencfg-branch-and-pr-settings.png?version=1&modificationDate=1647772253436&cacheVersion=1&api=v2&width=566&height=479)

## Personal access token

For more details on this setting, see [Require User PAT general setting](/git-integration-for-jira-data-center/require-user-pat-general-setting-gij-self-managed).

## Git branches

These settings will take effect at integration level for projects with connected GitLab/GitHub git hosts. The default state for each setting is _enabled_.

*   **Enable create/delete branch in Jira issues**  –  shows or hides the function for creating of branches. The ability to delete selected branches from the Jira developer panel is dependent on this setting.

*   **Branch name template**  –  see [below](#Branch-name-template).

*   **Branch name templates inner separator**  –  set which inner word separator to use for the branch name template. The default setting is `"-" (dash)`.

*   **Max branch name length**  –  specify the maximum character length for branch names. The default value is 250 chars.


## Branch name template

Set the **Branch name template** using the supported variables. Use the template to generate a default name for newly-created branches.

Use the following template variables:

`${issuetype}` – Issue Type. The Issue type is used to map a custom issue type as part of the template. The mapping pattern should look like this:

```java
${issuetype:type0,subsitute0[,type1,substitute1,...,typeN,substituteN][,defaultsubstitute]}
```

*   `typeN` – is the _**nth**_ issue type string to match.

*   `substituteN` – is the substitution string to use for _**typeN**_.

*   `defaultsubstitute` – is the substitution string to use if _**typeN**_'s match is not found. If _**defaultsubstitute**_ is blank, the lowercase version of the defined issue type is used.

`${issuekey}` – Issue Key. The Issue key is used in upper case.

`${summary}` – Issue Summary. The Summary is used and will be in lowercase; spaces are substituted by "-".

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>The Git Integration for Jira app default is:</b><br>
        `${issuekey}-${summary}`
        <p style='margin-bottom: 0px'>
            This generates the string format like "<b>PRJ-123-add-more-logging</b>" as a default value for the Create Branch and Pull/Merge Request dialogs. Where <code>PRJ-123</code> is the issue key followed by a hyphen then the summary text of the active issue page (<i>in hyphenated lowercase form</i>).
        </p>
    </div>
    </div>
</div>

`${projectkey}` – Project Key. The Project key is used and will be in uppercase.

`${basebranch}` – **INTRODUCED v4.0+** The base branch name is used.

* * *

### Some examples for branch templates

**Example 1:**<br>
`${issuetype}/${issuekey}-${summary}`

This generates the string format like "**newfeature/PRJ-123-add-more-logging**" as a default value for the branch names. Where `newfeature` is the actual issue type of the active Jira issue; in lowercase and trimmed of whitespaces, `PRJ-123` is the issue key followed by a hyphen then the summary text of the active issue page (in hyphenated lowercase form).

**Example 2:**<br>
`${issuetype:New Feature,feature,Bug Fix,bug}/${issuekey}-${summary}`

This generates the string format like "**feature/PRJ-123-add-more-logging**" as a default value for the branch names. This example uses a Jira issue which has the _**New Feature**_ issue type -- where `feature` is the substituted to _issuetype_ since _type0_ matches the active Jira issue type; `PRJ-123` is the issue key followed by a hyphen then the summary text of the active issue page (in hyphenated lowercase form).

**Example 3:**<br>
`${issuetype:Old Issue,old,Bug Fix,bug,branch}/${issuekey}-${summary}`

This generates the string format like "**branch/PRJ-123-add-more-logging**" as a default value for the branch names. This example uses a Jira issue which has the _**New Feature**_ issue type -- where `branch` is substituted to _issuetype_ since _type0..typeN_ does not match the active Jira issue type; `PRJ-123` is the issue key followed by a hyphen then the summary text of the active issue page (in hyphenated lowercase form).

* * *

## Git pull/merge requests

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828745/git-merge-pullreq-settings.png?version=1&modificationDate=1613124415741&cacheVersion=1&api=v2)

**Enable pull/merge request creation**  –  shows or hides the function for creating pull/merge requests from the Jira developer panel. This setting is ON by default.

**Enable indexing pull/merge requests via API**  –  This setting will index PR/MRs that are associated to Jira issues based on pull/merge request title which includes the Jira issue key. This setting is ON by default.

**Enable indexing pull/merge requests by commits**  –   This setting will index PR/MRs that are associated to Jira issues based on commits related to pull/merge requests with commit message containing a Jira issue key. This setting is `OFF` by default. Users will not be able to toggle this setting to ON/OFF if the _**Enable indexing pull/requests via API**_ is switched `OFF`.

When switched to `ON`, the _**Enable indexing pull/merge requests via API**_ setting completely activates the feature of indexing of PRs/MRs. This also allows users to use the toggle control for the _**Enable indexing pull/merge requests by commits**_ setting, which provides an additional way of indexing when switched to `ON`.

For detailed information on this feature, see article [Associate pull/merge requests in Jira Issue](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed).

