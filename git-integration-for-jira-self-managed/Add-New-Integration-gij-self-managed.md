---

title: Add New Integration - API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Adds a new integration to the git configuration list via the API call.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Add New Integration API call.
    </div>
    </div>
</div>
<br>

## Add new integration

_**url**_ -- `/rest/gitplugin/1.0/`**integration**

_**method**_ -- POST

### Parameters

Request body is a _JSON_ structure supporting the following parameters:

| **Parameter** | **Description** |
| :--- | :--- |
| _**displayName**_ | _String_. Optional. Some git hosts may require this to be filled in.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server. |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default setting for this field is _**false**_. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**type**_ | _String_. Required.<br><br>The type of integration. Available values are the following:<br><br>*   `GITHUB` - integration with Github.com<br>    <br>*   `GITHUB_SERVER` - integration with GitHub Enterprise<br>    <br>*   `GITLAB` - integration with GitLab.com<br>    <br>*   `GITLAB_SERVER` - integration with GitLab Server (CE/EE) (APIv4)<br>    <br>*   `GITLAB_SERVER_LEGACY` - integration with GitLab Server (CE/EE) Legacy (APIv3)<br>    <br>*   `FILESPACE` - integration for a tracked folder<br>    <br>*   `AZURE_DEVOPS` - integration with Azure DevOps Repos<br>    <br>*   `VSTS` - integration with Visual Studio Team Services (VSTS)<br>    <br>*   `AZURE` - integration with Azure DevOps Server<br>    <br>*   `TFS_SERVER` - integration with Team Foundation Server (TFS)<br>    <br>*   `AWS` - integration with AWS CodeCommit<br>    <br>*   `GERRIT` - integration with Gerrit Code Review |
| _**username**_ | _String._ Optional.<br><br>Set as username for the git host. Leave blank if 2FA is enabled. |
| _**password**_ | _String._ Optional.<br><br>Set as password for the git host. Leave blank if 2FA is enabled. |
| _**pat**_ | _String_. Optional.<br><br>This field accepts personal access token from supported git hosts. Fill this in if 2FA is enabled for the git host. |
| _**disableSslVerification**_ | _Boolean._ Optional.<br><br>The default value for this setting is _**false**_.<br><br>The **SSL Verify** setting is set to **Enabled** by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>![](/wp-content/uploads/bbb-tips-20.png) This setting can also be accessed via **Manage Git repositories** ➜ _Actions_ ➜ **Edit repository settings**. |
| _**apiPath**_ | _String_. Optional.<br><br>The integration will use the relative REST API path starting with "/" to retrieve the list of tracked repositories. For more information, see article [Working with Custom API path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed/). |
| _**apiFilter**_ | _String_. Optional.<br><br>It is a [**JMESPath**](http://jmespath.org/) filter expression. The expression will be used to filter API results such as repository names, etc. For more information, see article [Working with JMESPath filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed/). |
| _**tfsCollection**_ | _String_. Optional.<br><br>Specify the specific collection to connect. It is used for Microsoft integrations only. |
| _**awsRegion**_ | _String_. Optional.<br><br>Specify AWS region; where CodeCommit repositories are located. The list of regions with their names can be found [**here**](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).<br><br>Supported regions:<br><br>*   `us-east-1`<br>    <br>*   `us-east-2`<br>    <br>*   `us-west-1`<br>    <br>*   `us-west-2`<br>    <br>*   `ap-south-1`<br>    <br>*   `ap-northeast-2`<br>    <br>*   `ap-southeast-1`<br>    <br>*   `ap-southeast-2`<br>    <br>*   `ap-northeast-1`<br>    <br>*   `ca-central-1`<br>    <br>*   `eu-central-1`<br>    <br>*   `eu-west-1`<br>    <br>*   `eu-west-2`<br>    <br>*   `eu-west-3`<br>    <br>*   `eu-north-1`<br>    <br>*   `me-south-1`<br>    <br>*   `sa-east-1` |
| _**requireUserPat**_ | _Boolean_. Optional.<br><br>Setting this parameter to _**true**_ will require users to specify their own PAT for branch and pull/merge request management. |
| _**gitViewerEnabled**_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository. The default setting for this setting is _**enabled**_.<br><br>Users must have the **View Development Tools** _project permission_ in order to use this feature. Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed). |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is _**true**_. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the _projectMappingIds_ parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**revisionIndexing**_ | _Boolean_. Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed/). |
| _**projectMappingIds**_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository.<br><br>This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored _(equivalent to unchecking the_ **Associate to All Projects** _checkbox in the Advanced Setup dialog)_.<br><br>_Example:_ `“projectMappingIds”: [10000,10100]` |
| _**trustFolderStat**_ | _Boolean._ Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Data Center is **false**.<br><br>If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_.<br><br>We recommend to leave this setting to **false** _(default)_ when adding new integration. You can change this setting later on via _Actions_ ➜ _**Edit repository settings**_ in the Manage repositories page.<br><br>The `trustFolderStat` setting can be configured for each repository in the integration. |
| _**refSpecNotes**_ | _Boolean_. Optional.  <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br>Git notes are not shown…<br><br>*   when `refs/notes` are disabled on connecting a repository;<br>    <br>*   when a new note comes when `refs/notes` is disabled. |
| _**refSpecChanges**_ | _Boolean_. Optional.  <br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |

### Response

This will add a new integration of the connected git host to the git repository configuration list.

* * *

### Example:

`https://jira.yourorg.com/rest/gitplugin/1.0/`**integration**

```json
{
    "displayName": "MyGitHub",
    "origin": "https://api.github.com",
    "type": "GITHUB",
    "pat": "thisisthepatofyourgithost",
    "disabled": false,
    "sendCommitEmails": true,
    "maxMinsToCommitEmail": 1440,
    "global": true,    
    "revisionIndexing": true,
    "gitViewerEnabled": true,
    "disableSslVerification": false,
    "smartCommitsEnabled": true,
    "requireUserPat": false,
    "projectMappingIds": [],
    "sourcesDiffViewEnabled": true,
    "limitGitData": true,
    "refSpecNotes": true,
    "refSpecChanges": false,
    "trustFolderStat": false
}
```

### Response:

```json
{
    "success": "true",
    "integration": {
        "id": 1,
        "displayName": "MyGitHub",
        "origin": "https://api.github.com",
        "disabled": false,
        "sendCommitEmails": true,
        "maxMinsToCommitEmail": 1440,
        "global": true,
        "initDate": 1626070678087,
        "revisionIndexing": true,
        "gitViewerEnabled": true,
        "disableSslVerification": false,
        "smartCommitsEnabled": true,
        "requireUserPat": false,
        "projectMappingIds": [],
        "integrationType": "GITHUB",
        "sourcesDiffViewEnabled": true,
        "refSpecNotes": true,
        "refSpecChanges": false,
        "trustFolderStat": false
    }
}
```

