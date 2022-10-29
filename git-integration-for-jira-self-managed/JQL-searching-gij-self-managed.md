---

title: JQL searching
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Git Integration for Jira app has added JQL operators and fields to query Jira using JQL and git context via the Jira search.

## Enable/disable JQL search feature

Go to ![](/wp-content/uploads/actions-icon.png) Jira Administration ➜ Applications ➜ **General settings**.

<img src='/wp-content/uploads/gij-gitserver-gencfg-jql-search-loc2.png' style='display:block;margin:25px auto;max-width:100%' />

This general setting allows administrators to enable/disable the JQL functions within the Git Integration for Jira app.

## JQL field syntax

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

## Exporting JQL search results

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

<p>&nbsp;</p>

<br>
<br>

[**Prev:** Reindexing](/git-integration-for-jira-data-center/reindexing-gij-self-managed)

[**Next:** Integration webhooks](/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed)


