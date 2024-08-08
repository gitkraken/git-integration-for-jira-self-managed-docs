---

title: GIJ Application Operations and Planning
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Integration Types
**Full Featured vs. Webhook Indexing**

The majority of our clients use the“Full Featured” or “Webhook Indexing” integration. Full featured integrations are active 2 way connections, while Webhook indexing integrations are one way passive connections. To decide which is best for your organization, consider the following 2 factors:

1. Company policy regarding cloning code
2. Private vs Public Git Server

Full Featured integrations are our recommended integration type for clients, as this will allow you to utilize our full feature set. If your git server is behind a firewall/proxy, you can still utilize this integration type, but you will have to do some whitelisting of our IP’s, and make sure that the URL for your git service is publicly routable: [Allowlist - GIJ Cloud](https://help.gitkraken.com/git-integration-for-jira-cloud/allow-list-whitelist-bigbrassband-cloud-gij-cloud/)

Note, Full featured integrations requires GIJ to clone your repositories in order to provide Code Compare and Code Diff functionality directly from Jira. Repositories will be cloned to our AWS storage and, to a directory assigned specifically for your install. All traffic/data is encrypted in transit and at rest. Consider visiting our [Security and Trust](https://www.gitkraken.com/git-integration-for-jira/security-and-trust) page for an overview of our security measures. 

Webhook Indexing integrations are designed to accommodate clients with security restrictions surrounding Code cloning, or for clients utilizing self-hosted git servers placed behind firewalls/proxies and cannot make those servers routable from the public internet. Details about how Webhook Indexing integrations work can be found [here](https://help.gitkraken.com/git-integration-for-jira-cloud/webhook-indexing-explainer-gij-cloud/). While this option addresses key security restrictions, this integration type has a limited feature set due to its reliance on webhooks delivered from your git service containing only basic git data for Jira Issue updates. 

The full feature matrix between the integration types can be found [here](https://help.gitkraken.com/git-integration-for-jira-cloud/feature-matrix-of-git-integration-for-jira-cloud-gij-cloud/).


**Plain Git Connections**
If you are not using one of the major Git services (GitHub, GitLab, Azure DevOps, Bitbucket,  AWS), we still have you covered! We support plain git connections to each individual repository you wish to roll up into your Jira issues. Please see the feature matrix linked above for details on the limitations on plain git connections.

# Indexing Behavior
Now that you have determined what kind of integration type fits your needs, let’s learn how Git Integration for Jira indexes updates from your repositories.
**Full Featured Integrations**
By default, full featured integrations go through 2 different stages of indexing, initial indexing which only happens once, and normal indexing.

**First Time Indexing**
The initial indexing phase only happens the first time that an integration is added to GIJ, or a new repository is added to an existing integration. This initial indexing phase is comprised of 2 different actions:

1. Clone all of your repositories/ the newly created repository. 
2. Scan the entire Git history for each repository searching for Jira issues.

This scan allows us to link any Git data that previously referenced Jira issues in the appropriate places in order to provide the most comprehensive historical Git data in Jira possible. Because we are performing more intensive operations, this initial indexing phase tends to take more time than subsequent indexes. The total index time varies greatly for users, but in general demands more time for repositories with  longer Git histories, or with many branches and pull/merge requests. The number of repositories included in the integration will also have an impact on this indexing time.

**Normal Indexing Operations**
After all of your integrations/repositories have been indexed for the 1st time, the application will automatically index your Git repositories periodically based on an adaptive timer. The index frequency will vary based on a few different factors, such as how often there are changes detected in that repository, but most active repositories will be indexed every 20 minutes or so. The amount of time that it takes GIJ to complete all of the indexing tasks will also affect the indexing frequency. For a more comprehensive explanation of our indexing process, please see [Classic Indexing explainer](https://help.gitkraken.com/git-integration-for-jira-cloud/classic-indexing-explainer-gij-cloud/)

**Indexing Triggers**
We suggest utilizing [Indexing Triggers](https://help.gitkraken.com/git-integration-for-jira-cloud/indexing-triggers-gij-cloud/) alongside your integrations. These indexing triggers are webhooks that are created/sent from your repositories whenever there are updates to your repositories. When we receive the webhook, we will automatically index that repository outside of the normal indexing timer, allowing near real-time updates.

**Webhook Indexing**
Despite the name, there is no actual indexing taking place when utilizing Webhook Indexing integrations. Since this is a one-way passive integration, we do not clone/scan/index your repositories at any point. Instead, we rely on metadata included in the webhooks themselves to update the Jira Issues. With webhook indexing:

- No specific code change information is sent 
- No repository information is sent 
- Repository record is added after a webhooks is received

GIJ only updates Jira issues when we receive webhooks from your repositories containing Jira issue keys as part of the changes. There is no periodic or scheduled indexing. This means that all changes are updated in near real time by default.


## Integration structure planning
Now that you have a better understanding of what to expect with GIJ, consider taking some time to evaluate how to structure your integrations such as:. 
1. Total Number of Repositories you wish to connect to Jira.
    - The higher the number of connected repositories, the more challenging it can become to manage them, especially if you wish to utilize project associations. 
    - The more repository connections, the more likely you are to run into rate limiting issues as well.
2. The structure of your repositories in your Git services. 
    - Do you have your repositories organized by organization/groups in your Git service, or is everything included in a single group/org? The more structured your repositories, the easier it becomes to create integrations.

Consider creating multiple integrations to the same Git service, each connecting to a different org/group instead of one large integration containing all of your repositories. If you only have less than 100, then this might not be necessary for your needs, but if you have more than 100, and wish to limit visibility between Jira projects, then it will be easier to manage if they are broken up over multiple integrations.

Usually the best way to do this is to create an integration per Org/group, as long as the total number of repositories included in each integration is less than 2000. If a group/org has more than 2000 repos, then you will have to create multiple integrations to that same org/group in order to get the total number of repos to around 2000 or less. This can be done either by manually selecting the repositories in the UI, or by applying [Custom API Path](https://help.gitkraken.com/git-integration-for-jira-cloud/working-with-custom-api-path-gij-cloud/) and/or [JMESPath filtering](https://help.gitkraken.com/git-integration-for-jira-cloud/working-with-jmespath-filters-gij-cloud/) .

Rate limiting can become an issue for large instances when there are a large number of repositories included, or some of the repositories have long and complex Git histories with a lot of Branches and or Pull/Merge requests. If this is a concern for your instance, then the best way to address it will vary based on a few factors, but the general suggestion is to generate multiple service accounts on your Git service, and spread out the authentication for your various integrations across the different accounts. Since the API calls will then be spread out across more accounts, and over a longer period of time, this should help avoid hitting your Git services rate limits.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        
Note, there are some soft performance limitations to consider when planning your integrations, so please review our known Performance Limitations page for some guidelines to follow when planning out your integrations. <a href='/git-integration-for-jira-cloud/known-performance-limitations-gij-cloud/'>Click here</a>
    </div>
    </div>
</div>

___

[<b style='background-color:#FFFCC3; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>NEXT</b>](/git-integration-for-jira-cloud/Getting-Started-Guide-Integration-Creation-Post-Integration-Config) <a href="https://help.gitkraken.com/git-integration-for-jira-cloud/Getting-Started-Guide-Integration-Creation-Post-Integration-Config/">Integration Creation and Post Integration Config</a>

[<b style='background-color:#F1F1F1; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>PREVIOUS</b>](/git-integration-for-jira-cloud/Getting-Started-Guide/) <a href="https://help.gitkraken.com/git-integration-for-jira-cloud/Getting-Started-Guide/">Getting Started</a>
