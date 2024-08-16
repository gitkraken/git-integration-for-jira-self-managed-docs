---

title: GIJ Integration creation and Post integration Configuration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Integration Creation
---
### Creating your integrations
Ready for the fun part? It is time to create your integrations! For detailed step by step instructions on how to create the integrations by Git service, please refer to our Integration guides [Integration Guides](https://help.gitkraken.com/git-integration-for-jira-data-center/integration-guides-gij-self-managed/).

All of the planning and decision making from the previous steps get put to work during the integration creation process. You should now have confidence choosing which repositories to include, and which Project Association permissions to apply to limit visibility. We suggest that you disable any features that you will not be using before creating your integrations as discussed previously.

If using multiple integrations, consider creating only one or two integrations at a time. Additionally, please wait until the initial indexing phase completes for the new integration before going through the process of creating the next one. This reduces the probability of rate limiting issues or overloading the application with a large backlog of tasks. 

While this suggested approach may take a bit longer to complete, it avoids common issues or quickly raises important issues to address before committing the time to create all of your integrations. For any such issues, contact our support team  to work through the problem and save time.


## Post Integration creation configuration
---
Now that you have created all of your integrations, we recommend the following actions to round out your configuration.

### Edit Integration feature settings
**Display name**
We suggest editing each of your integrations and modifying the display name to better reflect what is included, or what org/group is connected. Please see [Edit Integration connection settings](https://help.gitkraken.com/git-integration-for-jira-data-center/edit-integration-connection-settings-gij-self-managed/) for details.

**Require user PAT**
We strongly recommend enabling the “require user PAT” integration setting. This option will require all of your users to provide their own PAT the first time they go to create a branch or pull/merge request from inside Jira. 

This is important, as we will then use their PAT to authenticate newly created branches and pull/merge requests and  attribute them to the correct user on your Git Service. If this option is not enabled, the branch/pull/merge request will still be created, but it will be authenticated using the integration connection credentials, and will be attributed to whatever account the credentials are associated with. Please see [Require Personal Access Tokens](https://help.gitkraken.com/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed/) for further details.

**Enforce Git Service Permission**
We strongly recommend that you enable the ‘Enforce Git service permissions” option if you are using the ‘Require User Pat’ option. This setting will pull the repo permission for each user that provides their PAT, and will only show them Git data that they have permission to. Please see [Enforce Git Service Permissions](https://help.gitkraken.com/git-integration-for-jira-data-center/enforce-git-service-permissions-gij-self-managed/) for details.

### Tuning the Reindexing interval
Once your integrations are all been configured, and they have indexed successfully for a day or two, we suggest that you go in and tune your reindex interval. To do this, you will need to use the Indexing queue viewer to see how long your indexing is taking. Once you know  your previous indexing duration, set the reindex interval to a few minutes more than the duration value. Please [Recommended reindex Interval](https://help.gitkraken.com/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed/) for details.

___

[<b style='background-color:#FFFCC3; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: medium;'>NEXT</b>](/git-integration-for-jira-data-center/Getting-Started-Guide-Optional-Features-dc) <a href="https://help.gitkraken.com/git-integration-for-jira-data-center/Getting-Started-Guide-Optional-Features-dc/">Optional Features and Add-on Extensions</a>

[<b style='background-color:#F1F1F1; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: medium;'>PREVIOUS</b>](/git-integration-for-jira-data-center/git-integration-for-jira-data-center/Getting-Started-Guide-App-operations-and-planning-dc/) <a href="https://help.gitkraken.com/git-integration-for-jira-data-center/git-integration-for-jira-data-center/Getting-Started-Guide-App-operations-and-planning-dc/">Application operations and planning</a>
