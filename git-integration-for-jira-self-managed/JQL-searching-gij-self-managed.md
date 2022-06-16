---

title: JQL searching
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

**INTRODUCED VERSION 2.6.9+**

The Git Integration for Jira app has added JQL operators and fields to query Jira using JQL and git context via the Jira search.

## Enable/disable JQL search feature

Go to Jira Administration ➜ Applications ➜ **General settings**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399338/gitserver-gencfg-jql-search-loc2.png?version=1&modificationDate=1630642933115&cacheVersion=1&api=v2&width=680&height=613)

This general setting allows administrators to enable/disable the JQL functions within the Git Integration for Jira app.

## JQL field syntax

The Jira JQL has been extended as follows:

| **Criteria Name** | **JQL Field Syntax** | **Description** | **Search Result Value Example** |
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

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399338/jql-search-export-context.png?version=1&modificationDate=1630642932417&cacheVersion=1&api=v2)

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

