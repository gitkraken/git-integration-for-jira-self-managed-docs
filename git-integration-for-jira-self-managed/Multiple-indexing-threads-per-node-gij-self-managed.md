---

title: Multiple Indexing Threads - General setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>NEW FEATURE</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>ADMINS</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>DATA CENTER ONLY</b>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Available in version Git Integration for Jira Data Center <b>v4.27+</b>.
    </div>
    </div>
</div>

Many git administrators express concerns regarding the performance issues associated with indexing repositories. Our current single-thread indexer has been found inadequate for effectively addressing this situation.

Starting GIJ version 4.72+, an extended feature has been introduced to support the use of multiple indexing threads for each node defined by the user for indexing. This enhancement is aimed at significantly improving the efficiency of the indexing procedure.

This feature allows the configuration of multiple indexing threads per node in the General Settings page. This new setting is introduced to consolidate all indexing threads from across all nodes.

<img src='/wp-content/uploads/gij-datacenter-number-of-indexing-nodes-general-setting.png' style='display:block;margin:25px auto;max-width:100%' />

Enter the required number of indexing threads per node. The default value is 1; maximum value is 100. This is the number of indexing threads available for updating repositories from remote git servers. Please note that this feature is experimental. Make sure to adjust this setting accordingly while taking into account the consequences if the hardware requirements do not align with the number of indexing threads.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Multi-threaded indexing may cause a slight delay for API responses.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Important</b><br>
        Additional indexing threads will require additional CPU and memory resources.
    </div>
    </div>
</div>

&nbsp;

### Rate limit throttling settings

HTTP code 429 (too many requests) is raised if the number of requests overwhelms the limit of the git service. Take into consideration that processing too many requests consumes more CPU and memory resources.

To avoid problems with excessive load on external git services, we introduced rate limit throttling. This feature allows administrators to configure the number of requests to external git services measured in requests per second (rps). Setting the value to zero (0) for the selected service will disable throttling for that git service.

<img src='/wp-content/uploads/gij-datacenter-external-services-throtlling-general-setting.png' style='display:block;margin:25px auto;max-width:100%' />

**For integrations from private git servers** -- this group setting is disabled by default. This is because private servers can be tailored to the organization's requirements and policies.

**For integrations from .com (cloud hosted)** -- this group setting is enabled by default. Make adjustments according to the cloud-hosted rules and limits.

Fix rate limit errors by reducing the number of requests to your git service. The above throttling settings allow administrators to configure the rate limit. This ensures that the Git server is not overloaded, especially with very large git integrations with the Jira instance.

The GIJ app is designed to efficiently receive and process all necessary data, regardless of any potential rate limits in place. It prioritizes maintaining the integrity and security of the data at every stage to avoid any risks of loss or corruption. Note that commits indexing will still work regardless of rate limit errors.

Refer to the table below as a basis for rate limiting:

| Git service | Rate limit |
|:---|:---|
| GitHub.com and GitHub Enterprise Cloud | 5000 requests per hour per user |
| GitHub App | 5000 requests per hour per user<br>Can be more, depending on conditions for user authentication and membership in the organization |
| GitHub Enterprise Server | Default: **_disabled_**<br>Depends on git admin setup or hardware resource limit |
| GitHub App Enterprise Server | Default: **_disabled_**<br>Depends on git admin setup or hardware resource limit |
| GitLab | 300 requests per minute |
| GitLab CE/EE | Default: **_disabled_**<br>Depends on git admin setup or hardware resource limit |
| Microsoft Cloud | 200 requests per 5 minutes |
| Microsoft On-premises | Default: **_disabled_**<br>Depends on git admin setup or hardware resource limit |

#### Repository hit rates

Track hit rates by reviewing current and maximum sizes in MB (megabytes):
*   Revision cache 
*   Branch cache
*   Tag cache size

#### GitHub rate limit throttling

After learning about GitHub's primary limits, GitHub also imposes secondary rate limits. These restrictions on concurrent calls from systems should be no more than...
*   100 concurrent requests allowed.
*   900 read requests per minute or 180 write requests per minute to a single REST endpoint.

The rate limit for GitHub Apps depends on whether the app authenticates with a user access token or an installation access token. It also depends on where the app is owned by or installed on a GitHub Enterprise Cloud organization.

For more information, see the following articles:

*   [Rate limits for the REST API](https://docs.github.com/en/rest/overview/rate-limits-for-the-rest-api)

*   [Rate limits and node limits for the GraphQL API](https://docs.github.com/en/graphql/overview/resource-limitations)

#### GitLab rate limit throttling

When the limit for the number of concurrent requests to GitLab is reached, a 429 error is returned. To perform another attempt, the client should wait for a bit. To learn more about GitLab rate limits, see [GitLab.com-specific rate limits](https://docs.gitlab.com/ee/user/gitlab_com/index.html#gitlabcom-specific-rate-limits).

### Microsoft rate limit throttling

Limit varies based on the pricing tier (e.g., Free, Shared, Basic, Standard, Premium)

Some Azure services have adjustable limits. The limit can be raised above the default limit but not above the maximum limit. Some limits are managed at a regional level. Note that free trial subscriptions are not eligible for limit increases.

For more information on Azure rate limits, see [Azure subscription and service limits, quotas and constraints](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits).

&nbsp;

### Factors influencing performance

Some factors that affects reindex performance:
*   number of branches
*   number of commits in a branch
*   number of git notes in the repositories
*   number of commit issue associations
*   commit notification emailing is enabled
*   smart commit is enabled
*   script execution is set up
*   the setting "Allow new commits to change LastUpdated field" is enabled
*   reindex queue size
*   reindexer idle time

Some factors that affect the Jira issue page loading performance:
*   Repository browser enabled
*   tags are displayed
*   number of tags and tag chains
*   number of repositories associated with a project
*   number of disabled repositories
*   the global setting "Enforce Git service permissions" is enabled

For Webhook performance, check the...
*   value of "Minimum repository reindex interval"
*   max. number of webhooks per hour from when you first use GIJ app
*   number of webhooks for the last hour or day
*   number of reindex tasks added by the webhook event

&nbsp;

### Optimizing repository indexing threads

<img src='/wp-content/uploads/gij-datacenter-number-of-indexing-nodes-general-setting.png' style='display:block;margin:25px auto;max-width:100%' />

The indexer has the capability to execute from 1 up to 100 repository indexing tasks concurrently on each node. The amount of threads can be configured on the "General settings" page under the "Number of indexing threads per node" field. Setting the right number of indexing threads is crucial to avoid surpassing your git service provider's rate limits.

We recommend to start with the default number of indexing threads. Incrementally increase the thread count to monitor indexing speed improvements while observing for rate limit issues or performance decline. This approach will help assess the performance impact and ensure stability before making further adjustments.

&nbsp;

## More on general settings

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

[Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-Code-Diff-Viewing-general-setting-gij-self-managed)

[Require User PAT general setting](/git-integration-for-jira-data-center/require-User-PAT-general-setting-gij-self-managed)

[Enforce Git service permissions setting](/git-integration-for-jira-data-center/enforce-Git-service-permissions-gij-self-managed)

[Git roll up issue tab setting](/git-integration-for-jira-data-center/git-roll-up-tab-setting-gij-self-managed)

[Git commits issue and project tabs setting](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

[Git integration features settings](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

[Enable Automation for Jira general setting](/git-integration-for-jira-data-center/enable-Automation-for-Jira-general-setting-gij-self-managed)

[Audit log settings](/git-integration-for-jira-data-center/audit-log-settings-gij-self-managed)

[Branch and pull request settings (formerly Git Integration Options)](/git-integration-for-jira-data-center/branch-and-pull-request-settings-(formerly-Git-Integration-Options)-gij-self-managed)

[Email settings](/git-integration-for-jira-data-center/email-settings-gij-self-managed)

[Scheduled jobs settings](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

[Per node repository indexing setting](/git-integration-for-jira-data-center/Per-Node-Repository-Indexing-gij-self-managed)

**Multiple indexing threads settings** (this page)

[Repositories garbage collection checker settings](/git-integration-for-jira-data-center/Repositories-garbage-collection-checker-gij-self-managed)

[Diff settings](/git-integration-for-jira-data-center/Diff-Settings-gij-self-managed)

[Discard cloned files in Jira HOME directory setting](/git-integration-for-jira-data-center/Discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

