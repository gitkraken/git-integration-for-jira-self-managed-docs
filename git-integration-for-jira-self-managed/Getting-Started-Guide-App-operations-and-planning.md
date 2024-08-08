---

title: GIJ Application Operations and Planning
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Integration Types
---
### Full Featured

Full featured integrations require GIJ clone your repositories to your Jira server in order to provide Code Compare and Code Diff functionality directly from Jira. Repositories will be cloned by the app to your Jira storage. These types of integrations are used to connect to all of the major Git Services such as GitHub, GitLab, Microsoft, AWS Code Commit or Gerrit self-hosted.

### Plain Git Connections
If you are not using one of the major Git services (GitHub, GitLab, Azure DevOps, AWS), we still have you covered! We support plain git connections to each individual repository you wish to roll up into your Jira issues. These types of connections are feature limited, not allowing branch/pull request creation, and not displaying any pull/merge request information.

### Storage
Git Integration for Jira clones all repositories included in an integration to your Jira Server, so you will need to make sure that your server has enough storage to accommodate the additional data. You will need at minimum the total amount of disk space used by all your repositories plus an additional 5% of space for our app data.


## Indexing Behavior
---
Now that you have determined what kind of integration type fits your needs, let’s learn how Git Integration for Jira indexes updates from your repositories.

### Full Featured Integrations
By default, full featured integrations go through 2 different stages of indexing, Initial or First time indexing which only happens once, and normal indexing.

### First time Indexing
The initial indexing phase only happens the first time that an integration is added to GIJ, or a new repository is added to an existing integration. This initial indexing phase is comprised of 2 different actions:
1. Clone all of your repositories/ the newly created repository. 
2. Scan the entire Git history for each repository searching for Jira issues.

This scan allows us to link any Git data that previously referenced Jira issues in the appropriate places in order to provide the most comprehensive historical git data in Jira possible. Because we are performing more intensive operations, this initial indexing phase tends to take more time than subsequent indexes. The total index time varies greatly for users, but in general demands more time for repositories with  longer Git histories, or with many branches and pull/merge requests. The number of repositories included in the integration will also have an impact on this indexing time.

### Normal Indexing Operations
GIJ operates on a configurable scheduled timer. GIJ will connect to your repository service and pull all updates from your repositories however often the reindex interval is set to. The indexing time will vary depending on your instance, so you will have to tune your indexing timer. We will discuss this process in more detail later on in this guide.

### Indexing Triggers
We suggest utilizing [Webhooks](https://help.gitkraken.com/git-integration-for-jira-data-center/webhooks-gij-self-managed/) alongside your integrations. These webhooks are sent from your repositories whenever there are updates to your repositories. When we receive the webhook, we will automatically index that repository outside of the normal indexing timer, allowing near real-time updates.

## Integration structure planning
---
Now that you have a better understanding of what to expect with GIJ, consider taking some time to evaluate how to structure your integrations such as: 
1. Total Number of Repositories you wish to connect to Jira.
- The higher the number of connected repositories, the more challenging it can become to manage them, especially if you wish to utilize project associations. 
- The more repository connections, the more likely you are to run into rate limiting issues as well.
2. The structure of your repositories in your Git services. 
- Do you have your repositories organized by organization/groups in your Git service, or is everything included in a single group/org? The more structured your repositories, the easier it becomes to create integrations.

Consider creating multiple integrations to the same Git service, each connecting to a different org/group instead of one large integration containing all of your repositories. If you only have fewer than 100 repos, then this might not be necessary for your needs. However if you do have more than 100 repos (and wish to limit visibility between Jira projects), then it will be easier to manage if they are broken up over multiple integrations.

Usually the best way to do this is to create an integration per org/group, as long as the total number of repositories included in each integration is less than 2000. If a group/org has more than 2000 repos, then you will have to create multiple integrations to that same org/group in order to get the total number of repos to around 2000 or less. This can be done by applying [Custom API Path](https://help.gitkraken.com/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed/)  and/or [JMESPath filtering](https://help.gitkraken.com/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed/).

Rate limiting can become an issue for large instances when there are a large number of repositories included, or some of the repositories have long and complex Git histories with a lot of Branches and or Pull/Merge requests. If this is a concern for your instance, then the best way to address it will vary based on a few factors, but the general suggestion is to generate multiple service accounts on your Git service, and spread out the authentication for your various integrations across the different accounts. Since the API calls will then be spread out across more accounts, and over a longer period of time, this should help avoid hitting your Git services rate limits.

**Features**
<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        
There are certain features in GIJ Data Center that we recommend you disable if you are not going to actively use them, as they can help improve performance and stability. Discuss if your team is interested in using JQL Searching, Git Tags, Smart commits, and commit notification emails. Please see <a href='/git-integration-for-jira-data-center/general-settings-improving-jira-performance-gij-self-managed/'>Improving Jira Performance</a> for further information on improving jira performance.    </div>
    </div>
</div>

___

[<b style='background-color:#FFFCC3; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>NEXT</b>](/git-integration-for-jira-data-center/Getting-Started-Guide-Integration-Creation-Post-Integration-Config) <a href="https://help.gitkraken.com/git-integration-for-jira-data-center/Getting-Started-Guide-Integration-Creation-Post-Integration-Config/">Integration Creation and Post Integration Config</a>

[<b style='background-color:#F1F1F1; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>PREVIOUS</b>](/git-integration-for-jira-data-center/Getting-Started-Guide/) <a href="https://help.gitkraken.com/git-integration-for-jira-data-center/Getting-Started-Guide/">Getting Started</a>
