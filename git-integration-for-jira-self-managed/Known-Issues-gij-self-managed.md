---

title: Known Issues
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Git Integration for Jira app is packed with features that makes Jira administrators and developers happy. However, with different hardware configurations out there, these great features can also become burdened by issues.

Below are the Git Integration app known issues and workarounds:
- [**2GB Object Git Repositories Storage Limit**](#2gb-object-git-repositories-storage-limit)
- [**Surpassing JQL 65K Jira Issues Searching Limitation**](#surpassing-jql-65k-jira-issues-searching-limitation)
- [**Commits Relating Only to Tags are Not Displayed**](#commits-relating-only-to-tags-are-not-displayed)
- [**Fully Cancelling an Ongoing Indexing is Not Possible**](#fully-cancelling-an-ongoing-indexing-is-not-possible)
- [**Microsoft Pull Request Requirement for Status Updates**](#microsoft-pull-request-requirement-for-status-updates)
- [**Why Microsoft PAT Integrations Require “All accessible organizations” Permission**](#why-microsoft-pat-integrations-require-all-accessible-organizations-permission)
- [**Enabling the App With Many Repositories Configured**](#enabling-the-app-with-many-repositories-configured)
- [**Pull Requests Changed Before Migration to v3.7 Do Not Trigger Workflow Hooks**](#pull-requests-changed-before-migration-to-v37-do-not-trigger-workflow-hooks)
- [**Deleted Merge Requests Not Removed from the Jira Issue Screen**](#deleted-merge-requests-not-removed-from-the-jira-issue-screen)
- [**Azure DevOps: Long Pull Request Descriptions Limited to 400 Characters**](#azure-devops-long-pull-request-descriptions-limited-to-400-characters)
- [**Gerrit Integration Connected with Errors**](#gerrit-integration-connected-with-errors)
- [**Starred repositories Custom API Path might fail if using SSO**](#starred-repositories-custom-api-path-might-fail-if-using-sso)

* * *

### **2GB Object Git Repositories Storage Limit**

The Git Integration for Jira application uses the JGit library which does not support objects over 2GB in size stored in git repositories.

*   2GB object limit

_Reference_: …

### **Surpassing JQL 65K Jira Issues Searching Limitation**

To increase the 65,000 issue JQL search limit:

1.  Create a `jira-config.properties` file under the `<JIRA-HOME>` directory, if it doesn't already exists.

2.  Add the `jira.search.maxclauses` property with the new value:

    ```java
    jira.search.maxclauses = 100000
    ```
For more information on this issue, see [**Atlassian KB - 65K issue limit in JQL functions - Time to SLA for Jira**](https://confluence.snapbytes.com/time-to-sla/knowledge-base/common-problems/65k-issue-limit-in-jql-functions).

Please contact [support@bigbrassband.com](mailto:support@bigbrassband.com) if you encounter related issues.

_Reference:_ GIT-3710, GITSERVER-1008

### **Commits Relating Only to Tags are Not Displayed**

During the commits indexing, the Git Integration app processes only branches. Thus, it only sees the commits belonging to any branch. However, if some commits relate only to tags, these commits will not be displayed.

_**Affected example:**_<br>
Jira ticket `ACME-123` has tag "`release3.5.1.3`" and commit "`5c0a97dfb7d28d4e3d1807c6f0869d8d90ae78b4`".

_Reference:_ GIT-3854

### **Fully Cancelling an Ongoing Indexing is Not Possible**

Cancelling indexing from the Git Integration admin interface is not currently possible. See **Workaround**.

**DISABLING A REPOSITORY OR INTEGRATION IN MANAGE GIT REPOSITORIES PAGE:**<br>
We tested disabling a repository or integration (integration level) on the Manage git repositories page and this action does not interrupt a reindex thread. This only stops the indexing of commits, branches and notes. The pull/merge request reindex are still processed and continues to do requests to an external service.

When a repository is disabled, the process is still ongoing while it skips indexing some of its entities.

**DISABLING THE GIT INTEGRATION FOR JIRA APP IN THE MANAGE APPS:**<br>
This action completely interrupts the indexing thread.

**WORKAROUND**<br>
To forcefully interrupt the indexing process, _**disable**_ the Git Integration for Jira app temporarily and then _**re-enable**_ it via the **Manage apps**.

_Reference:_ GIT-3847

### **Microsoft Pull Request Requirement for Status Updates**

Microsoft integrations require all pull requests for the configured repositories to be requested each time for status updates. Microsoft's Pull Request APIs do not currently provide any information allowing for filtering by last changed date/time.

_Reference:_ GIT-3889

### **Why Microsoft PAT Integrations Require “All accessible organizations” Permission**

It is highly required that administrators must select the “**All accessible organizations**” option when creating personal access tokens (PAT). Otherwise, the integration will not work.

Please follow the instructions for creating MS/Azure PATs outlined in our Confluence how-tos [**here**](/git-integration-for-jira-data-center/creating-personal-access-tokens/).

For more information, see the [**official reference for Azure DevOps PAT integration**](https://developercommunity.visualstudio.com/content/problem/902833/azure-devops-personal-access-token-does-).

_Reference:_ GIT-3978

### **Enabling the App With Many Repositories Configured**

Repositories are initialized upon enabling the Git Integration for Jira app. This initialization process can take several minutes when many repositories are configured.

We are working on an improvement to move this initialization process away from enabling/disabling the app.

_Reference:_ GIT-3977

### **Pull Requests Changed Before Migration to v3.7 Do Not Trigger Workflow Hooks**

Pull requests changed before migration to v3.7 do not trigger [workflow hooks](https://github.com/BigBrassBand/jira-git-workflow-hooks).

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We strongly suggest that you perform a "<b>Reindex All</b>" in the git manager page after the app upgrade to v3.7+.
    </div>
    </div>
</div>

_Reference:_ GIT-3989

### **Deleted Merge Requests Not Removed from the Jira Issue Screen**

The deleted merged requests are not removed as expected from the Jira Issue page after the app upgrade to v3.7+.

**Cause:** GitLab’s API responses do not contain sufficient information about deleted merge requests when requesting updated merge requests.

**WORKAROUND**<br>
To delete a Merge Request in GitLab and see results in Jira please reset the index of the relevant GitLab integration after the merge request deletion:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/591888396/reset-index-3.7.png?version=1&modificationDate=1600099525092&cacheVersion=1&api=v2)

_Reference:_ GIT-3989

### **Azure DevOps: Long Pull Request Descriptions Limited to 400 Characters**

Azure DevOps supports descriptions of pull requests with the maximum length of 4000 chars in the web interface. However, only the first 400 characters of an Azure DevOps Pull Request description are made are made available via the Azure DevOps API. As a result, the long PR descriptions appear to be cropped in the tooltip over a pull request on the Git Integration panel.

_Reference: GIT-3989_

### **Gerrit Integration Connected with Errors**

The standard Gerrit "All-Projects", "All-Users" and other parent repositories do not contain commits and JGit is not able to clone/index these repositories

**WORKAROUND**<br>
Jira administrators may specify the "`+refs/meta/*:refs/meta/*`" custom refs:

1.  For your connected integration in the Manage Git repositories page, go to &nbsp;<img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration connection settings**.

2.  Locate and click **Advanced ❯** (_just below JMESPath or TrustFolderStat option_) to see the _**refspec**_ options.

3.  Make the suggested changes and save/update this setting.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/591888396/gitserver-gerrit-kb-refspecs-wkaround.png?version=1&modificationDate=1650611506926&cacheVersion=1&api=v2&width=680&height=755)
    
_Reference:_ GIT-4111

### **Starred repositories Custom API Path might fail if using SSO**

The Custom API Path, `/users/<username>/starred`, could fail in returning the repository list for starred repositories with GitHub Enterprise git hosts that have enabled SSO (single sign-on) authentication.

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Error!</b><br>
        Caused by: org.eclipse.jgit.errors.TransportException: ...: git-upload-pack not permitted on ...
    </div>
    </div>
</div>

