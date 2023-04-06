---

title: Update Existing Integration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Updates the existing parameters of the specified integration.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Update Integration API call.
    </div>
    </div>
</div>
<br>

## Update Existing Integration

### url
`/rest/gitplugin/1.0/integration/\{integrationId\}`

### integrationId
_Integer_. Required.

This is the ID of the existing integration. For example, `/integration/3`.

Using the _**integrationId**_ from the url, the Update Integration API will look for the integration with `id : 3` and replaces integration properties according to the declared JSON request body structure file.

### method
PUT

### Parameters

The Request body is a _JSON_ structure similar to the [Add New Integration API](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed). Unlike the [Update Existing Repository API](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed), the `id` of the integration is substituted to the url as `integrationId`.

| Parameter | Condition |
| :--- | :--- |
| _**displayName**_ | _String_. Optional. Some git hosts may require this to be filled in.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Optional.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server.<br><br>_**Example URL:**_ `https://api.github.com` |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default value for this field is _**false**_. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**type**_ | _String_. Optional.<br><br>The type of integration. Available values are the following:<br><ul><li><code>GITHUB</code> - integration with Github.com</li><li><code>GITHUB_SERVER</code> - integration with GitHub Enterprise</li><li><code>GITLAB</code> - integration with GitLab.com</li><li><code>GITLAB_SERVER</code> - integration with GitLab Server (CE/EE) (APIv4)</li><li><code>GITLAB_SERVER_LEGACY</code> - integration with GitLab Server (CE/EE) Legacy (APIv3)</li><li><code>FILESPACE</code> - integration for a tracked folder</li><li><code>AZURE_DEVOPS</code> - integration with Azure DevOps Repos</li><li><code>VSTS</code> - integration with Visual Studio Team Services (VSTS)</li><li><code>AZURE</code> - integration with Azure DevOps Server</li><li><code>TFS_SERVER</code> - integration with Team Foundation Server (TFS)</li><li><code>AWS</code> - integration with AWS CodeCommit</li><li><code>GERRIT</code> - integration with Gerrit Code Review</li></ul> |
| _**username**_ | _String._ Optional.<br><br>Set as username for the git host. Leave blank if 2FA is enabled. |
| _**password**_ | _String._ Optional.<br><br>Set as password for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**pat**_ | _String._ Optional.<br><br>This field accepts personal access token from supported git hosts. Fill this in if 2FA is enabled for the git host and if the PAT has changed. |
| _**disableSslVerification**_ | _Boolean._ Optional.<br><br>The **SSL Verify** setting is set to `Enabled` by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br><img src='/wp-uploads/content/bbb-tips-20.png' /> This setting can also be accessed via Manage Git repositories ➜ _Actions_ ➜ **Edit Integration settings**. |
| _**apiPath**_ | _String_. Optional.<br><br>The integration will use the relative REST API path starting with "/" to retrieve the list of tracked repositories. For more information, see article [Working with Custom API path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed). |
| _**apiFilter**_ | _String_. Optional.<br><br>It is a [**JMESPath**](http://jmespath.org/) filter expression. The expression will be used to filter API results such as repository names, etc. For more information, see article [Working with JMESPath filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed). |
| _**tfsCollection**_ | _String_. Optional.<br><br>Specify the specific collection to connect. It is used for Microsoft integrations only. |
| _**awsRegion**_ | _String_. Optional.<br><br>Specify AWS region; where CodeCommit repositories are located. The list of regions with their names can be found [**here**](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).<br><br>Supported regions:<br><ul><li><code>us-east-1</code></li><li><code>us-east-2</code></li><li><code>us-west-1</code></li><li><code>us-west-2</code></li><li><code>ap-south-1</code></li><li><code>ap-northeast-2</code></li><li><code>ap-southeast-1</code></li><li><code>ap-southeast-2</code></li><li><code>ap-northeast-1</code></li><li><code>ca-central-1</code></li><li><code>eu-central-1</code></li><li><code>eu-west-1</code></li><li><code>eu-west-2</code></li><li><code>eu-west-3</code></li><li><code>eu-north-1</code></li><li><code>me-south-1</code></li><li><code>sa-east-1</code></li></ul> |
| _**requireUserPat**_ | _Boolean_. Optional.<br><br>Setting this parameter to _**true**_ will require users to specify their own PAT for branch and pull/merge request management. |
| **_gitViewerEnabled_** | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository. The default setting for this setting is _**enabled**_.<br><br><img src='/wp-content/uploads/bbb-alert-20.png' /> Users must have the **View Development Tools** _project permission_ in order to use this feature. Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed). |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is _**true**_. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the _projectMappingIds_ parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**revisionIndexing**_ | _Boolean_. Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed). |
| _**projectMappingIds**_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository. When you create a new repository and set the field _gitViewerEnabled_ to **true**, at least one project must be associated with it. |
| _**trustFolderStat**_ | _Boolean_. Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Data Center is **false**.<br><br><img src='/wp-content/uploads/bbb-note-20.png' /> If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_.<br><br><img src='/wp-content/uploads/bbb-tips-20.png' /> The `trustFolderStat` setting can be configured for each repository in the integration. |
| _**refSpecNotes**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br>Git notes are not shown…<br><ul><li>when `refs/notes` are disabled on connecting a repository;</li><li>when a new note comes when `refs/notes` is disabled.</li></ul> |
| _**refSpecChanges**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.<br><br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |
| _**folderDepth**_ | _Integer_. Optional. <br>Valid value range: 1 - 5 <br>This parameter is required if _**integrationType**_ = `FILESPACE`. |

### Response

Updates the recent changes of the parameters for the specified integration.

**Example 1:**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/integration/1`

Request body (JSON) example:

```json
{
  "displayName": "MY GITLAB",
  "origin": "https://gitlab.com",
  "disabled": false,
  "sendCommitEmails": true,
  "maxMinsToCommitEmail": 1440,
  "global": true,
  "pat": "thisisthepatofyourgithost",
  "revisionIndexing": true,
  "gitViewerEnabled": true,
  "disableSslVerification": false,
  "smartCommitsEnabled": true,
  "requireUserPat": false,
  "projectMappingIds": [],
  "integrationType": "GITLAB",
  "sourcesDiffViewEnabled": true,
  "refSpecNotes": true,
  "refSpecChanges": false,
  "trustFolderStat": false,
}
```

Response:

```json
{
    "success": "true",
    "integration": {
        "id": 1,
        "displayName": "MY GITLAB",
        "origin": "https://gitlab.com",
        "disabled": false,
        "sendCommitEmails": true,
        "maxMinsToCommitEmail": 1440,
        "global": true,
        "initDate": 1574747787950,
        "lastIndexedDate": 1584720012000,
        "revisionIndexing": true,
        "gitViewerEnabled": true,
        "disableSslVerification": false,
        "smartCommitsEnabled": true,
        "projectMappingIds": [],
        "integrationType": "GITLAB",
        "sourcesDiffViewEnabled": true,
        "refSpecNotes": true,
        "refSpecChanges": false,
        "trustFolderStat": false
    }
}
```

<br>

**Example 2: Restrict an integration to project(s)**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/integration/1`

Request body (JSON) example:

```json
{
  "id": 1,
  "pat": "thisisthepatofyourgithost",  
  "gitViewerEnabled": true,  
  "smartCommitsEnabled": true,
  "global": false,
  "projectMappingIds": [ 10000 ],  
}

// The endpoint does not accept the "projectMappingIds" list when "global" is set to 'true'.
```

Response:

```json
{
    "success": "true",
    "integration": {
        "id": 1,
        "displayName": "MY GITLAB",
        "origin": "https://gitlab.com",
        "disabled": false,
        "sendCommitEmails": true,
        "maxMinsToCommitEmail": 1440,
        "global": false,
        "initDate": 1574747787950,
        "lastIndexedDate": 1584720012000,
        "revisionIndexing": true,
        "gitViewerEnabled": true,
        "disableSslVerification": false,
        "smartCommitsEnabled": true,
        "projectMappingIds": [ 10000 ],
        "integrationType": "GITLAB",
        "sourcesDiffViewEnabled": true,
        "refSpecNotes": true,
        "refSpecChanges": false,
        "trustFolderStat": false
    }
}
```

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

**Update Existing Integration** (this page)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

[Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

