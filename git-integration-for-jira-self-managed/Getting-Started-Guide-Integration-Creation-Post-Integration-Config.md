---

title: GIJ Integration creation and Post integration Configuration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Integration Creation
**Choosing Authentication type**
Next, let’s  decide which Authentication option is best for you. You can choose either PAT or OAuth based authentication with full featured integrations, but please note that the availability of authentication options can vary by Git service. Functionally, in most cases both options will work, without much difference.

If it is available, we recommend  OAuth authentication, as this allows some automatic actions to be taken by GIJ depending on the permissions level of the account used as well as the Git service. In some cases, this will allow GIJ to automatically create indexing triggers for your repositories, saving you some time and effort.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you are utilizing multiple service accounts for authentication, you will have to use an incognito/private browser window when creating the integrations so that you can sign in using the different accounts and avoid the cached credentials being used, which will result in the same account being associated with the integration
    </div>
    </div>
</div>

PAT authentication tends to be easier to maintain on an organizational level, especially when using multiple service accounts, as the Git Service Admins should have easy access to the accounts to generate the PATs. For detailed instructions on how to create Personal Access tokens, please see [here](https://help.gitkraken.com/git-integration-for-jira-cloud/creating-personal-access-tokens-gij-cloud).


**Creating your Integrations**
Ready for the fun part? It is time to create your integrations! For detailed step by step instructions on how to create the integrations by Git service, please refer to our Integration guides. The guides for full featured integrations can be found [here](https://help.gitkraken.com/git-integration-for-jira-cloud/integration-guide-gij-cloud/). The Webhook Indexing integration guides are [here](https://help.gitkraken.com/git-integration-for-jira-cloud/webhook-indexing-integration-gij-cloud/)

All of the planning and decision making from the previous steps get put to work during the integration creation process. You should now have confidence choosing your authentication type, which repositories to include, and which Project Association permissions to apply to limit visibility. 

If using multiple integrations, consider creating only one or two integrations at a time. Additionally, please wait until the initial indexing phase completes for the new integration before going through the process of creating the next one. This reduces the probability of rate limiting issues or overloading the application with a large backlog of tasks. 

While this suggested approach may take a bit longer to complete, it avoids common issues or quickly raises important issues to address before committing the time to create all of your integrations. For any such issues, contact our support team  to work through the problem and save time.


## Post Integration creation configuration
Now that you have created all of your integrations, we recommend the following actions   to round out your configuration.

**Edit Integration feature settings**
**Display Name**
 We suggest editing each of your integrations and modifying the display name to better reflect what is included, or what org/group is connected. 

**Require user PAT**
We strongly recommend enabling the “require user PAT” integration setting. This option will require all of your users to provide their own PAT the first time they go to create a branch or pull/merge request from inside Jira. 

This is important, as we will then use their PAT to authenticate newly created branches and pull/merge requests and  attribute them to the correct user on your Git Service. If this option is not enabled, the branch/pull/merge request will still be created, but it will be authenticated using the integration connection credentials, and will be attributed to whatever account the credentials are associated with. Please see [Require Personal Access Tokens](https://help.gitkraken.com/git-integration-for-jira-cloud/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-cloud/) for further details.

___

[<b style='background-color:#FFFCC3; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>NEXT</b>](/git-integration-for-jira-cloud/Getting-Started-Guide-Optional-Features) <a href="https://help.gitkraken.com/git-integration-for-jira-cloud/Getting-Started-Guide-Optional-Features/">Optional Features and Add-on Extensions</a>

[<b style='background-color:#F1F1F1; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>PREVIOUS</b>](/git-integration-for-jira-cloud/Getting-Started-Guide-Integration-Creation-Post-Integration-Config) <a href="https://help.gitkraken.com/git-integration-for-jira-cloud/Getting-Started-Guide-Integration-Creation-Post-Integration-Config/">Integration creation and Post integration Configuration</a>
