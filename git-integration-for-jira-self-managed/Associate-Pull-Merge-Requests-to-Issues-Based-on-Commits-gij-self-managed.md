---

title: Associate Pull/Merge Requests to Issues Based on Commits
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- This falls under Features sidenav -->

## Introduction

Starting with **v3.7.2+** of the Git Integration for Jira Server and Data Center app, we have added a new setting that allows for pull request (PR) and merge request (MR) indexing via API in **General Settings**. Additionally, in earlier versions, automatic indexing of PR/MRs cannot be avoided for auto-connect integrations.

Pull/merge requests appear automatically in the Git Integration panel based on the commits associated with the pull/merge request. This allows users who did not mention a Jira issue key in the PR/MR title or description, they will still be linked.

## Getting Started

The following settings are implemented in the **Manage git repositories** page ➜ **General settings** under **Git pull/merge requests**:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/966852625/jira-server-general-settings-branch-pull-req-cfgs%20(c).png?version=1&modificationDate=1608167565785&cacheVersion=1&api=v2)

### Enable pull/merge request creation in Jira issues

This setting will show or hide the function for creating pull/merge requests from the Jira developer panel. This setting is `ON` by default.

### Enable indexing pull/merge requests via API

This setting will index PR/MRs that are associated to Jira issues _**based on pull/merge request title**_ which includes the Jira issue key. This setting is ON by default.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Turn off this setting for improved Jira performance. Note that the API calls increase the number of calls to the git server – by one additional API call per each merge/pull request.
    </div>
    </div>
</div>

There are corresponding API calls to get merge/pull request commits, at least in the below integrations:

*   [GitHub](https://developer.github.com/v3/pulls/#list-commits-on-a-pull-request)

*   [GitLab](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits)

*   [Azure/TFS](https://docs.microsoft.com/en-us/rest/api/azure/devops/git/pull%20request%20commits/get%20pull%20request%20commits?view=azure-devops-rest-6.0#response)

### Enable indexing pull/merge requests by commits

This setting will index PR/MRs that are associated to Jira issues _**based on commits**_ related to pull/merge requests with _**commit message containing**_ a Jira issue key. This setting is `OFF` by default. Users will not be able to toggle this setting to **ON/OFF** if the _**Enable indexing pull/requests via API**_ is switched `OFF`.

Turning this setting `ON` does not call commits on acquiring for existing pull/merge requests in their unchanged state. As a result, the Git Integration app won’t be filling the commit association information for already connected integrations.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Commits will be indexed for new/changed PR/MRs only. This will significantly reduce the number of calls to the git server. The current implementation automatically detects changes even for Microsoft pull requests which doesn’t have the <b><i>lastUpdateTime</i></b> field.
    </div>
    </div>
</div>

* * *

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        
    </div>
    </div>
</div>

When switched to <code>ON</code>, the <b><i>Enable indexing pull/merge requests via API</i></b> setting completely activates the feature of indexing of PRs/MRs. This also allows users to use the toggle control for the <b><i>Enable indexing pull/merge requests by commits</i></b> setting, which provides an additional way of indexing when switched to ON.

## Guidelines

### What to do with the rate limit issues?

With the index settings above, the rate limit issues can be ignored. At least, the user may turn the feature off, connect an integration, wait until the reindexing is completed, and then turn the feature back on.

### Do I need to do a Reset index?

The commits for existing PR/MRs are not needed to be retrieved again, so there’s no need to do a reset index.

### Will this affect repositories with webhooks? Will webhooks trigger reindexing a repository via API to get PRs via commits?

Yes, Any indexing of repo (manually, via API, webhooks) will call reindexing a repository to get PRs via commits

## Recommendations

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We highly recommend setting the <b>Reindex Interval</b> setting (in General Settings) to no longer than every 24hrs when possible.
    </div>
    </div>
</div>
<br>
