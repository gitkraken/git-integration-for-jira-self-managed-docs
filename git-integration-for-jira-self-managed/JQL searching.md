---

title: JQL searching
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
JIRA SERVER JIRA DATA CENTER

INTRODUCED VERSION 2.6.9+

The Git Integration for Jira app has added JQL operators and fields to query Jira using JQL and git context via the Jira search.

## Enable/disable JQL search feature INTRODUCED  _v2.12.0+_

Go to Jira Administration ➜ Applications ➜ **General settings**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399338/gitserver-gencfg-jql-search-loc2.png?version=1&modificationDate=1630642933115&cacheVersion=1&api=v2&width=680&height=613)

This general setting allows administrators to enable/disable the JQL functions within the Git Integration for Jira app.

## JQL field syntax

The Jira JQL has been extended as follows:

| **Criteria Name** | **JQL Field Syntax** | **Description** | **Search Result Value Example** |
| --- | --- | --- | --- |
| Git Commits Referenced | `gitCommitsReferenced` is not empty<br><br>`gitCommitsReferenced` is empty | True for all issues referenced by a git commit<br><br>True for all issues not referenced by a git commit | `True` or “” _(empty string)_ |
| Git Branch | `gitBranch` in (`Version-5.2`, `Version-5.3`) | True for all issues referenced by a git commit in branch Version-5.2 and branch Version-5.3 | `Version-5.2,` `Version-5.3` |

| **Examples:** |
| --- |
| ```java<br>gitBranch in (master) AND resolution = Unresolved<br>gitCommitsReferenced is not empty AND resolution = Unresolved<br>``` |

## Exporting JQL search results

You can save the JQL search results to CSV, HTML, XML or Word via **Export**.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399338/jql-search-export-context.png?version=1&modificationDate=1630642932417&cacheVersion=1&api=v2)

JQL searching will not work if more than **65,000 Jira issues** have at least one git commit associated. For more detailed information, see [Known issues – JQL searching limitation](/git-integration-for-jira-self-managed/known-issues#JQL-Searching-Limitation).
