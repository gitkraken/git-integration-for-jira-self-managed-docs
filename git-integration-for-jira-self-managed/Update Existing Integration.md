---

title: Update Existing Integration
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Updates the existing parameters of the specified integration.

Only Jira admins can perform the Update Integration API call.

|     |     |
| --- | --- |
| **Update Existing Integration** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**integration**`/`**{integrationId}** |     |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/3`.<br><br>Using the _**integrationId**_ from the url, the Update Integration API will look for the integration with `id : 3` and replaces integration properties according to the declared JSON request body structure file. |
| _**method**_ |     |
| PUT |     |
| _**parameters**_ |     |
| The Request body is a _JSON_ structure similar to the [Add New Integration API](/wiki/spaces/GIJDC/pages/380666461/Add+New+Integration). Unlike the [Update Existing Repository API](/wiki/spaces/GIJDC/pages/380699263/Update+Existing+Repository), the `id` of the integration is substituted to the url as `integrationId`. |     |
| **Parameter** | **Condition** |
| _**displayName**_ | _String_. Optional. Some git hosts may require this to be filled in.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Optional.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server.<br><br>_**Example URL:**_ `https://api.github.com` |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default value for this field is _**false**_. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**type**_ | _String_. Optional.<br><br>The type of integration. Available values are the following:<br><br>*   `GITHUB` - integration with Github.com<br>    <br>*   `GITHUB_SERVER` - integration with GitHub Enterprise<br>    <br>*   `GITLAB` - integration with GitLab.com<br>    <br>*   `GITLAB_SERVER` - integration with GitLab Server (CE/EE) (APIv4)<br>    <br>*   `GITLAB_SERVER_LEGACY` - integration with GitLab Server (CE/EE) Legacy (APIv3)<br>    <br>*   `FILESPACE` - integration for a tracked folder<br>    <br>*   `AZURE_DEVOPS` - integration with Azure DevOps Repos<br>    <br>*   `VSTS` - integration with Visual Studio Team Services (VSTS)<br>    <br>*   `AZURE` - integration with Azure DevOps Server<br>    <br>*   `TFS_SERVER` - integration with Team Foundation Server (TFS)<br>    <br>*   `AWS` - integration with AWS CodeCommit<br>    <br>*   `GERRIT` - integration with Gerrit Code Review |
| _**username**_ | _String._ Optional.<br><br>Set as username for the git host. Leave blank if 2FA is enabled. |
| _**password**_ | _String._ Optional.<br><br>Set as password for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**pat**_ | _String._ Optional.<br><br>This field accepts personal access token from supported git hosts. Fill this in if 2FA is enabled for the git host and if the PAT has changed. |
| _**disableSslVerification**_ | _Boolean._ Optional.<br><br>The **SSL Verify** setting is set to `Enabled` by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via **Manage Git repositories** ➜   <br>![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Actions_ ➜ **Edit Integration settings**. |
| _**apiPath**_ | _String_. Optional.<br><br>The integration will use the relative REST API path starting with "/" to retrieve the list of tracked repositories. For more information, see article [Working with Custom API path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path). |
| _**apiFilter**_ | _String_. Optional.<br><br>It is a [**JMESPath**](http://jmespath.org/) filter expression. The expression will be used to filter API results such as repository names, etc. For more information, see article [Working with JMESPath filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters). |
| _**tfsCollection**_ | _String_. Optional.<br><br>Specify the specific collection to connect. It is used for Microsoft integrations only. |
| _**awsRegion**_ | _String_. Optional.<br><br>Specify AWS region; where CodeCommit repositories are located. The list of regions with their names can be found [**here**](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).<br><br>Supported regions:<br><br>*   `us-east-1`<br>    <br>*   `us-east-2`<br>    <br>*   `us-west-1`<br>    <br>*   `us-west-2`<br>    <br>*   `ap-south-1`<br>    <br>*   `ap-northeast-2`<br>    <br>*   `ap-southeast-1`<br>    <br>*   `ap-southeast-2`<br>    <br>*   `ap-northeast-1`<br>    <br>*   `ca-central-1`<br>    <br>*   `eu-central-1`<br>    <br>*   `eu-west-1`<br>    <br>*   `eu-west-2`<br>    <br>*   `eu-west-3`<br>    <br>*   `eu-north-1`<br>    <br>*   `me-south-1`<br>    <br>*   `sa-east-1` |
| _**requireUserPat**_ | _Boolean_. Optional.<br><br>Setting this parameter to _**true**_ will require users to specify their own PAT for branch and pull/merge request management. |
| #### _gitViewerEnabled_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository. The default setting for this setting is _**enabled**_.<br><br>Users must have the **View Development Tools** _project permission_ in order to use this feature. Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser). |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is _**true**_. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the [_projectMappingIds_](#projectMappingIds) parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**revisionIndexing**_ | _Boolean_. Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/wiki/spaces/GIJDC/pages/1930399204/Git+tags). |
| _**projectMappingIds**_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository. When you create a new repository and set the field [_gitViewerEnabled_](#gitViewerEnabled) to **true**, at least one project must be associated with it. |
| _**trustFolderStat**_ | _Boolean_. Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Data Center is **false**.<br><br>If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_.<br><br>The `trustFolderStat` setting can be configured for each repository in the integration. |
| _**refSpecNotes**_ | _Boolean_. Optional.  <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br>Git notes are not shown…<br><br>*   when `refs/notes` are disabled on connecting a repository;<br>    <br>*   when a new note comes when `refs/notes` is disabled. |
| _**refSpecChanges**_ | _Boolean_. Optional.  <br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |
| _**response**_ |     |
| Updates the recent changes of the parameters for the specified integration. |     |

|     |
| --- |
| **Example 1:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**`/`**1**<br><br>Request body (JSON) example:<br><br>```java<br>{<br>  "displayName": "MY GITLAB",<br>  "origin": "https://gitlab.com",<br>  "disabled": false,<br>  "sendCommitEmails": true,<br>  "maxMinsToCommitEmail": 1440,<br>  "global": true,<br>  "pat": "thisisthepatofyourgithost",<br>  "revisionIndexing": true,<br>  "gitViewerEnabled": true,<br>  "disableSslVerification": false,<br>  "smartCommitsEnabled": true,<br>  "requireUserPat": false,<br>  "projectMappingIds": [],<br>  "integrationType": "GITLAB",<br>  "sourcesDiffViewEnabled": true,<br>  "refSpecNotes": true,<br>  "refSpecChanges": false,<br>  "trustFolderStat": false,<br>}<br>```<br><br>Response:<br><br>```java<br>{<br>    "success": "true",<br>    "integration": {<br>        "id": 1,<br>        "displayName": "MY GITLAB",<br>        "origin": "https://gitlab.com",<br>        "disabled": false,<br>        "sendCommitEmails": true,<br>        "maxMinsToCommitEmail": 1440,<br>        "global": true,<br>        "initDate": 1574747787950,<br>        "lastIndexedDate": 1584720012000,<br>        "revisionIndexing": true,<br>        "gitViewerEnabled": true,<br>        "disableSslVerification": false,<br>        "smartCommitsEnabled": true,<br>        "projectMappingIds": [],<br>        "integrationType": "GITLAB",<br>        "sourcesDiffViewEnabled": true,<br>        "refSpecNotes": true,<br>        "refSpecChanges": false,<br>        "trustFolderStat": false<br>    }<br>}<br>``` |

|     |
| --- |
| **Example 2: Restrict an integration to project(s)** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**`/`**1**<br><br>Request body (JSON) example:<br><br>```java<br>{<br>  "id": 1,<br>  "pat": "thisisthepatofyourgithost",  <br>  "gitViewerEnabled": true,  <br>  "smartCommitsEnabled": true,<br>  "global": false,<br>  "projectMappingIds": [ 10000 ],  <br>}<br><br>// The endpoint does not accept the "projectMappingIds" list when "global" is <br>set to 'true'.<br>```<br><br>Response:<br><br>```java<br>{<br>    "success": "true",<br>    "integration": {<br>        "id": 1,<br>        "displayName": "MY GITLAB",<br>        "origin": "https://gitlab.com",<br>        "disabled": false,<br>        "sendCommitEmails": true,<br>        "maxMinsToCommitEmail": 1440,<br>        "global": false,<br>        "initDate": 1574747787950,<br>        "lastIndexedDate": 1584720012000,<br>        "revisionIndexing": true,<br>        "gitViewerEnabled": true,<br>        "disableSslVerification": false,<br>        "smartCommitsEnabled": true,<br>        "projectMappingIds": [ 10000 ],<br>        "integrationType": "GITLAB",<br>        "sourcesDiffViewEnabled": true,<br>        "refSpecNotes": true,<br>        "refSpecChanges": false,<br>        "trustFolderStat": false<br>    }<br>}<br>``` |

### Related articles

*   Page:

    [Add New Integration](/wiki/spaces/GIJDC/pages/380666461/Add+New+Integration) (Git Integration for Jira Data Center)

*   Page:

    [Add New Integration Type API (examples)](/wiki/spaces/GIJDC/pages/380666468) (Git Integration for Jira Data Center)

*   Page:

    [Update Existing Integration](/wiki/spaces/GIJDC/pages/380699347/Update+Existing+Integration) (Git Integration for Jira Data Center)

*   Page:

    [Remove Integration](/wiki/spaces/GIJDC/pages/380797346/Remove+Integration) (Git Integration for Jira Data Center)

*   Page:

    [Retrieve an Integration](/wiki/spaces/GIJDC/pages/380699382/Retrieve+an+Integration) (Git Integration for Jira Data Center)

*   Page:

    [Retrieve Integration List](/wiki/spaces/GIJDC/pages/380666487/Retrieve+Integration+List) (Git Integration for Jira Data Center)