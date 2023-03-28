---

title: Add New Integration API
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

### url
`/rest/gitplugin/1.0/`**integration**

### method
POST

### Parameters

Request body is a _JSON_ structure supporting the following parameters:

| Parameter | Description |
| :--- | :--- |
| _**displayName**_ | _String_. Optional. Some git hosts may require this to be filled in.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server. |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default setting for this field is _**false**_. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**type**_ | _String_. Required.<br><br>The type of integration. Available values are the following:<ul><li><code>GITHUB</code> - integration with Github.com</li><li><code>GITHUB_SERVER</code> - integration with GitHub Enterprise</li><li><code>GITLAB</code> - integration with GitLab.com</li><li><code>GITLAB_SERVER</code> - integration with GitLab Server (CE/EE) (APIv4)</li><li><code>GITLAB_SERVER_LEGACY</code> - integration with GitLab Server (CE/EE) Legacy (APIv3)</li><li><code>FILESPACE</code> - integration for a tracked folder</li><li><code>AZURE_DEVOPS</code> - integration with Azure DevOps Repos</li><li><code>VSTS</code> - integration with Visual Studio Team Services (VSTS)</li><li><code>AZURE</code> - integration with Azure DevOps Server</li><li><code>TFS_SERVER</code> - integration with Team Foundation Server (TFS)</li><li><code>AWS</code> - integration with AWS CodeCommit</li><li><code>GERRIT</code> - integration with Gerrit Code Review</li></ul> |
| _**username**_ | _String._ Optional.<br><br>Set as username for the git host. |
| _**password**_ | _String._ Optional.<br><br>Set as password for the git host. |
| _**pat**_ | _String_. Optional.<br><br>This field accepts personal access token from supported git hosts. |
| _**disableSslVerification**_ | _Boolean._ Optional.<br><br>The default value for this setting is _**false**_.<br><br>The **SSL Verify** setting is set to **Enabled** by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><div class="bbb-callout bbb--tip"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">This setting can also be accessed via Manage Git repositories ➜ <img src='/wp-content/uploads/actions-icon.png' /> <i>Actions</i> ➜ <b>Edit repository settings</b>.</div></div></div> |
| _**apiPath**_ | _String_. Optional.<br><br>The integration will use the relative REST API path starting with "/" to retrieve the list of tracked repositories. For more information, see article [Working with Custom API path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed/). |
| _**apiFilter**_ | _String_. Optional.<br><br>It is a [**JMESPath**](http://jmespath.org/) filter expression. The expression will be used to filter API results such as repository names, etc. For more information, see article [Working with JMESPath filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed/). |
| _**tfsCollection**_ | _String_. Optional.<br><br>Specify the specific collection to connect. It is used for Microsoft integrations only. |
| _**awsRegion**_ | _String_. Optional.<br><br>Specify AWS region; where CodeCommit repositories are located. The list of regions with their names can be found [**here**](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).<br><br>Supported regions:<ul><li><code>us-east-1</code></li><li><code>us-east-2</code></li><li><code>us-west-1</code></li><li><code>us-west-2</code></li><li><code>ap-south-1</code></li><li><code>ap-northeast-2</code></li><li><code>ap-southeast-1</code></li><li><code>ap-southeast-2</code></li><li><code>ap-northeast-1</code></li><li><code>ca-central-1</code></li><li><code>eu-central-1</code></li><li><code>eu-west-1</code></li><li><code>eu-west-2</code></li><li><code>eu-west-3</code></li><li><code>eu-north-1</code></li><li><code>me-south-1</code></li><li><code>sa-east-1</code></li></ul> |
| _**requireUserPat**_ | _Boolean_. Optional.<br><br>Setting this parameter to _**true**_ will require users to specify their own PAT for branch and pull/merge request management. |
| _**gitViewerEnabled**_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository. The default setting for this setting is _**enabled**_.<br><div class="bbb-callout bbb--alert"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">Users must have the <b>View Development Tools</b> <i>project permission</i> in order to use this feature. Consult your Jira System Administrator on permissions.</div></div></div><br>For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed). |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is _**true**_. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the _projectMappingIds_ parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**revisionIndexing**_ | _Boolean_. Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed/). |
| _**projectMappingIds**_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository.<br><br>This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored _(equivalent to unchecking the_ **Associate to All Projects** _checkbox in the Advanced Setup dialog)_.<br><br>_Example:_ `“projectMappingIds”: [10000,10100]` |
| _**trustFolderStat**_ | _Boolean._ Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Data Center is **false**.<br><div class="bbb-callout bbb--note"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your repository is stored on a network share, it is highly recommended to set this setting to <b><i>false</i></b>.</div></div></div><div class="bbb-callout bbb--tip"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">We recommend to leave this setting to <code>false</code> <i>(default)</i> when adding new integration. You can change this setting later on via &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit repository settings</b> in the Manage repositories page.</div></div></div><div class="bbb-callout bbb--tip"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">The <code>trustFolderStat</code> setting can be configured for each repository in the integration.</div></div></div> |
| _**refSpecNotes**_ | _Boolean_. Optional. <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">Git notes are not shown…<br><ul><li>when <code>refs/notes</code> are disabled on connecting a repository;</li><li>when a new note comes when <code>refs/notes</code> is disabled.</li></ul></div></div></div> |
| _**refSpecChanges**_ | _Boolean_. Optional. <br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional. <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |
| _**folderDepth**_ | _Integer_. Optional. <br>Valid value range: 1 - 5 <br>This parameter is required if _**integrationType**_ = `FILESPACE`. |

<br>

### Response

This will add a new integration of the connected git host to the git repository configuration list.

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

<br>

**Response:**

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

<br>

### Integration REST APIs

**Add New Integration** (this page)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

[Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

