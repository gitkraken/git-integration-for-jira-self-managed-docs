---

title: JQL searching
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Git Integration for Jira app has added JQL operators and fields to query Jira using JQL and git context via the Jira search.

&nbsp;

### Enable/disable JQL search feature

Go to ![](/wp-content/uploads/actions-icon.png) Jira Administration ➜ Applications ➜ **General settings**.

<img src='/wp-content/uploads/gij-gitserver-gencfg-jql-search-loc2.png' style='display:block;margin:25px auto;max-width:100%' />

This general setting allows administrators to enable/disable the JQL functions within the Git Integration for Jira app.

### JQL field syntax

The Jira JQL has been extended as follows:

| Criteria Name | JQL Field Syntax | Description | Search Result Value Example |
| :--- | :--- | :--- | :--- |
| Git Commits Referenced | `gitCommitsReferenced` is not empty<br>`gitCommitsReferenced` is empty | True for all issues referenced by a git commit<br>True for all issues not referenced by a git commit | `True` or “” _(empty string)_ |
| Git Branch | `gitBranch` in (`Version-5.2`, `Version-5.3`) | True for all issues referenced by a git commit in branch Version-5.2 and branch Version-5.3 | `Version-5.2,` `Version-5.3` |

**Examples:**<br>
```java
gitBranch in (master) AND resolution = Unresolved
gitCommitsReferenced is not empty AND resolution = Unresolved
```

&nbsp;

<table style="border-size: 1px;">
    <tr>
        <td style="padding:10px;">
            <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.28+</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 5.1+</b><br><br>    
            The <code>gitCommitsReferenced</code> field now additionally supports project filtering.<br><br>
            The resulting set in the response to the user's request has not changed. The only difference is that, before, the project filter is applied only after the filter. Now, it is applied inside the filter as well.<br><br>
            See the JQL query with the project filter together with the <code>gitCommitReferenced</code> field below:<br><br>
            <code>project = ISSUE_KEY AND gitCommitsReferenced is EMPTY</code>
        </td>
    </tr>
</table>

&nbsp;

### Exporting JQL search results

You can save the JQL search results to CSV, HTML, XML or Word via **Export**.

<img src='/wp-content/uploads/gij-jql-search-export-context.png' style='display:block;margin:25px auto;max-width:100%' />

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        JQL searching will not work if more than <b>65,000 Jira issues</b> have at least one git commit associated. For more detailed information, see <a href='/git-integration-for-jira-data-center/known-issues-gij-self-managed#surpassing-jql-65k-jira-issues-searching-limitation'>Known issues – JQL searching limitation</a>.
    </div>
    </div>
</div>

&nbsp;

### We’re getting no response anymore from JQL searches and when we try, we see CPU spikes. What's causing this?

JQL has some limitations. Having more than 65,000 active Jira issues may cause the query to timeout. In some cases, it is better to add more conditions to narrow down the number of results.

For example, you can try inverting the order of the query:<br>
`gitCommitsReferenced = true AND project = XXX`

&nbsp;
* * *

[**Prev:** Reindexing](/git-integration-for-jira-data-center/reindexing-gij-self-managed)

[**Next:** Integration webhooks](/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed)


