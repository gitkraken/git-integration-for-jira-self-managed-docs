---

title: Associate Pull/Merge Requests to Issues Based on Commits
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
GIT INTEGRATION: JIRA DATA CENTER

## Introduction

Starting with VERSION 3.7.2+ of the Git Integration for Jira Server and Data Center app, we have added a new setting that allows for pull request (PR) and merge request (MR) indexing via API in **General Settings**. Additionally, in earlier versions, automatic indexing of PR/MRs cannot be avoided for auto-connect integrations.

Pull/merge requests appear automatically in the Git Integration panel based on the commits associated with the pull/merge request. This allows users who did not mention a Jira issue key in the PR/MR title or description, they will still be linked.

## Getting Started

The following settings are implemented in the **Manage git repositories** page ➜ **General settings** under **Git pull/merge requests**:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/966852625/jira-server-general-settings-branch-pull-req-cfgs%20(c).png?version=1&modificationDate=1608167565785&cacheVersion=1&api=v2)

|     |
| --- |
| **Enable pull/merge request creation in Jira issues** |
| This setting will show or hide the function for creating pull/merge requests from the Jira developer panel. This setting is ON by default. |

|     |
| --- |
| **Enable indexing pull/merge requests via API** |
| This setting will index PR/MRs that are associated to Jira issues _**based on pull/merge request title**_ which includes the Jira issue key. This setting is ON by default.<br><br>Turn off this setting for improved Jira performance. Note that the API calls increase the number of calls to the git server – by one additional API call per each merge/pull request.<br><br>There are corresponding API calls to get merge/pull request commits, at least in the below integrations:<br><br>*   GitHub – [https://developer.github.com/v3/pulls/#list-commits-on-a-pull-request](https://developer.github.com/v3/pulls/#list-commits-on-a-pull-request)<br>    <br>*   GitLab – [https://docs.gitlab.com/ee/api/merge\_requests.html#get-single-mr-commits](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits)<br>    <br>*   Azure/TFS – [https://docs.microsoft.com/en-us/rest/api/azure/devops/git/pull%20request%20commits/get%20pull%20request%20commits?view=azure-devops-rest-6.0#response](https://docs.microsoft.com/en-us/rest/api/azure/devops/git/pull%20request%20commits/get%20pull%20request%20commits?view=azure-devops-rest-6.0#response) |

|     |
| --- |
| **Enable indexing pull/merge requests by commits** |
| This setting will index PR/MRs that are associated to Jira issues _**based on commits**_ related to pull/merge requests with _**commit message containing**_ a Jira issue key. This setting is OFF by default. Users will not be able to toggle this setting to ON/OFF if the _**Enable indexing pull/requests via API**_ is switched OFF.<br><br>Turning this setting ON does not call commits on acquiring for existing pull/merge requests in their unchanged state. As a result, the Git Integration app won’t be filling the commit association information for already connected integrations.<br><br>Commits will be indexed for new/changed PR/MRs only. This will significantly reduce the number of calls to the git server. The current implementation automatically detects changes even for Microsoft pull requests which doesn’t have the _**lastUpdateTime**_ field. |

When switched to ON, the _**Enable indexing pull/merge requests via API**_ setting completely activates the feature of indexing of PRs/MRs. This also allows users to use the toggle control for the _**Enable indexing pull/merge requests by commits**_ setting, which provides an additional way of indexing when switched to ON.

## Guidelines

### What to do with the rate limit issues?

With the index settings above, the rate limit issues can be ignored. At least, the user may turn the feature off, connect an integration, wait until the reindexing is completed, and then turn the feature back on.

### Do I need to do a Reset index?

The commits for existing PR/MRs are not needed to be retrieved again, so there’s no need to do a reset index.

### Will this affect repositories with webhooks? Will webhooks trigger reindexing a repository via API to get PRs via commits?

Yes, Any indexing of repo (manually, via API, webhooks) will call reindexing a repository to get PRs via commits

## Recommendations

We highly recommend setting the **Reindex Interval** setting (in General Settings) to no longer than every 24hrs when possible.