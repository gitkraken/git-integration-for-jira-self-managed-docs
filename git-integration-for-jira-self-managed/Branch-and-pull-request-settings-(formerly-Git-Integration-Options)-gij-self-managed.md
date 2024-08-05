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
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

This setting affects git branches creation default names and toggles for git pull/merge request options for the Jira issue.

<img src='/wp-content/uploads/gij-gitserver-gencfg-branch-and-pr-settings-group.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

### Personal access token

For more details on this setting, see [Require User PAT general setting](/git-integration-for-jira-data-center/require-user-pat-general-setting-gij-self-managed).

&nbsp;

### Git branches

These settings will take effect at integration level for projects with connected GitLab/GitHub git hosts. The default state for each setting is _enabled_.

*   **Enable create/delete branch in Jira issues**  –  shows or hides the function for creating of branches. The ability to delete selected branches from the Jira developer panel is dependent on this setting.

*   **Branch name template**  –  see [below](#Branch-name-template).

*   **Branch name templates inner separator**  –  set which inner word separator to use for the branch name template. The default setting is `"-" (dash)`.

*   **Max branch name length**  –  specify the maximum character length for branch names. The default value is 250 chars.

&nbsp;

### Branch name template

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
        <code>${issuekey}-${summary}</code>
        <p style='margin-bottom:-10px'>
            This generates the string format like "<b>PRJ-123-add-more-logging</b>" as a default value for the Create Branch and Pull/Merge Request dialogs. Where <code>PRJ-123</code> is the issue key followed by a hyphen then the summary text of the active issue page (<i>in hyphenated lowercase form</i>).
        </p>
    </div>
    </div>
</div>

`${projectkey}` – Project Key. The Project key is used and will be in uppercase.

`${basebranch}` – **INTRODUCED v4.0+** The base branch name is used.

&nbsp;

#### Some examples for branch templates

**Example 1:**<br>
`${issuetype}/${issuekey}-${summary}`

This generates the string format like "**newfeature/PRJ-123-add-more-logging**" as a default value for the branch names. Where `newfeature` is the actual issue type of the active Jira issue; in lowercase and trimmed of whitespaces, `PRJ-123` is the issue key followed by a hyphen then the summary text of the active issue page (in hyphenated lowercase form).

**Example 2:**<br>
`${issuetype:New Feature,feature,Bug Fix,bug}/${issuekey}-${summary}`

This generates the string format like "**feature/PRJ-123-add-more-logging**" as a default value for the branch names. This example uses a Jira issue which has the _**New Feature**_ issue type -- where `feature` is the substituted to _issuetype_ since _type0_ matches the active Jira issue type; `PRJ-123` is the issue key followed by a hyphen then the summary text of the active issue page (in hyphenated lowercase form).

**Example 3:**<br>
`${issuetype:Old Issue,old,Bug Fix,bug,branch}/${issuekey}-${summary}`

This generates the string format like "**branch/PRJ-123-add-more-logging**" as a default value for the branch names. This example uses a Jira issue which has the _**New Feature**_ issue type -- where `branch` is substituted to _issuetype_ since _type0..typeN_ does not match the active Jira issue type; `PRJ-123` is the issue key followed by a hyphen then the summary text of the active issue page (in hyphenated lowercase form).

&nbsp;

### Git pull/merge requests

<img src='/wp-content/uploads/gij-datacenter-git-pull-merge-req-group-gencfg.png' style='display:block;margin:25px auto;max-width:100%' />

**Enable pull/merge request creation in Jira issues**<br>
Shows or hides the function for creating pull/merge requests from the Jira developer panel. This setting is `ON` by default.

**Enable indexing pull/merge requests via API**<br>
This feature indexes pull requests/merge requests linked to Jira issues through their titles containing the Jira issue key. By default, this feature is enabled.

This setting controls user accessibility to other Git PR/MR settings such as:
*   Share PR/MR events information with TIJ
*   Share PR/MR author information with TIJ
*   Enable indexing PR/MR by commits

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Note that to be able to view the new GitHub share PR events, we recommend that users must update their personal access token to have the following scopes:<br>
        <ul style='margin-bottom:-10px'>
            <li><code>read:discussion</code></li>
            <li><code>read:org</code></li>
            <li><code>read:user</code></li>
            <li><code>repo</code> (all)</li>
            <li><code>user:email</code></li>
        </ul>
    </div>
    </div>
</div>

<img src='/wp-content/uploads/gij-datacenter-enable-indexing-pmreq-via-api-group-gencfg.png' style='display:block;margin:25px auto;max-width:100%' />

**Share pull/merge request events information with Team Insights for Jira**<br>
This feature allows GIJ indexing PR/MR events data which can be utilized by the TIJ extension. When utilizing a GitHub service, the specified scopes (mentioned above) are mandatory. By default, this setting is configured as `OFF`.

Click on **> Advanced** to expand more options for this setting.

| Option      | Description |
|:------------|:------------|
| Event limit | **No limits**<br>If this option is selected, GIJ will read all available PR/MR events data from history. This setting could impact Jira performance.<br><br>**Limit the period**<br>If this setting is selected, the next setting options becomes available and can be configured manually. |
| Max event age in days | Required.<br>Specify the duration, in days, during which PR events information will be processed. Only PR events occurring within this defined period will be considered and used. Events that fall outside of this timeframe will be excluded and will not be processed. The default value is **90 days**. |
| Pull requests events reindex interval | Required.<br>Enter the frequency for reindexing PR events by specifying a time interval in seconds. A minimum time interval is necessary between each reindexing operation to reduce performance impact.<br><br>This setting specifically applies to integrations with Microsoft products. It does not impact reindexing processes for integrations with different systems or platforms. The default value is **14400 seconds (4 hours)**.

**Share pull/merge request author information with Team Insights for Jira**
This feature allows the TIJ extension to either activate or deactivate the retrieval of PR/MR author details from GIJ. GitHub users must have the specified scopes (mentioned above) to utilize this option. By default, this setting is configured as OFF.

**Enable indexing pull/merge requests by commits**<br>
This setting enables the indexing of pull requests and merge requests linked to Jira issues through commits made in pull/merge requests. Specifically, it focuses on commits that include a Jira issue key within their commit messages. This setting is `OFF` by default.

Users will not be able to access this setting if the _**Enable indexing pull/requests via API**_ setting is switched `OFF`.

For detailed information on this feature, see article [Associate pull/merge requests in Jira Issue](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed).

&nbsp;

### More on General settings

[Git roll up issue tab](/git-integration-for-jira-data-center/git-roll-up-tab-setting-gij-self-managed)

[Git commits issue and project tabs](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

[Git integration features](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

**Branch and pull request settings (formerly Git Integration Options)** (this page)

[Email settings](/git-integration-for-jira-data-center/email-settings-gij-self-managed)

[Scheduled jobs](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

[Audit log settings](/git-integration-for-jira-data-center/audit-log-settings-gij-self-managed)

[General settings](/git-integration-for-jira-data-center/general-Settings-gij-self-managed)

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

[Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-Code-Diff-Viewing-general-setting-gij-self-managed)

[Enforce Git service permissions](/git-integration-for-jira-data-center/enforce-Git-service-permissions-gij-self-managed)

[Enable Automation for Jira general setting](/git-integration-for-jira-data-center/enable-Automation-for-Jira-general-setting-gij-self-managed)

[Require User PAT general setting](/git-integration-for-jira-data-center/require-User-PAT-general-setting-gij-self-managed)

