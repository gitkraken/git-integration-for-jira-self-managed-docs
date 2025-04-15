---

title: Update Nested Repository API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Updates the existing nested repository using the REST API.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Update Nested Repository API call.
    </div>
    </div>
</div>

### url
`{JiraBaseURL}/rest/gitplugin/1.0/repository`

### method
PUT

### Parameters

The Request body is a _JSON_ structure similar to the [Update Existing Repository API](/git-integration-for-jira-data-center/update-existing-repository-gij-self-managed) plus the _**id**_ parameter:

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        In the table below, fields marked with a <b>Read-only</b> flag cannot be changed. Any defined value is ignored.
    </div>
    </div>
</div>

| Field | Description |
| :--- | :--- |
| _**id**_ | Integer. Required.<br><br>This is the ID of the existing nested repository. For example, `id : 3,`.<br><br>The Update Repository API will look for the repository with `id : 3` and replaces repository properties according to the declared JSON request body structure file. |
| _**displayName**_ | _String._ Optional.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**mainBranch**_ | _String._ Read-only.<br><br>The specified branch will intend to organize the Git Commit tab. A commit will not be shown in other branches if it is a part of the main branch. By default, "master" will be used if a main branch is not specified. |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default setting for this field is _**false**_.<br><br><b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px 10px 0; font-size: small;display:inline-block;'>UPDATE</b><br>Use the separate API for enabling/disabling a repository which is better and more reliable than using this field here. For detailed instructions on the usage, see [Enable/disable existing repository API](/git-integration-for-jira-data-center/Enable-disable-existing-repository-API-gij-self-managed) page. |
| _**enableFetches**_ | _Boolean._ Read-only.<br><br>Set to _**true**_ to enable fetches on git repositories hosted on remote servers.<br><br>Set to _**false**_ to enable fetches on git repositories hosted on the same server as Jira. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer._ Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the _projectMappingIds_ parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**projectMappingIds**_ | _Long [ ]._ Array. Optional.<br><br>These are numeric projects IDs associated with the repository. When you create a new repository and set the field gitViewerEnabled to true, at least one project must be associated with it.<br><br>Example: `"projectMappingIds": [10000]` |
| _**hosted**_ | **Internal field**. Read-only.<br><br>This field will show whether the repository is hosted on Jira or not. |
| _**revisionIndexing**_ | _Boolean._ Optional.<br><br>This setting turn on/off indexing of revisions, for instance, git commits. This setting also turns on the memory cache which is used when list of commits are displayed.<br><br>Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| **_gitViewerEnabled_** | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository.  The default setting for this setting is _**enabled**_. Users must have the **View Development Tools** _project permission_ in order to use this feature.  Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed). |
| _**username**_ | _String._ Read-only.<br><br>Set as username for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**encryptedPassword**_ | _String._ Read-only.<br><br>Set as password for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**encryptedPat**_ | _String._ Read-only.<br><br>This field accepts personal access token from supported git hosts. Fill this in if 2FA is enabled for the git host and if the PAT has changed. |
| _**requireUserPat**_ | _String._ Read-only. Default is _**false**_.<br><br>Setting this field to true will require users to provide their personal access tokens (PAT) specific for branch and pull/merge request operations. |
| _**disableSslVerification**_ | _Boolean._ Read-only.<br><br>The **SSL Verify** setting is set to _**false**_ by default. If set to _**true**_, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via:<br><br><b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.8.x</b> **Manage repositories** ➜ _Actions_ ➜ **Edit repository settings**.<br><br><b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 5+</b> **Manage integrations** ➜ _Actions_ ➜ **Edit repository**. |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default setting for this field is _**true**_. |
| _**webLinkType**_ | _String._ Optional.<br><br>Set web link type equivalent to the connected git host. Set web linking formats by referring to [Git Integration for Jira: Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed). |
| _**viewFormat**_ | _String._ Optional.<br><br>This URL is unused and not being configured for the newly added integration types. |
| _**changesetFormat**_ | _String._ Optional.<br><br>This is the URL used to display revision.<br><br>Use the following variable: `${rev}` &nbsp;&ndash;&nbsp; git revision |
| _**fileAddedFormat,**_  <br>_**fileModifiedFormat**_,  <br>_**fileDeletedFormat**_ | _String._ Optional.<br><br>This is the URL to display content of added, modified or deleted files. Use the following variables:<br><br><ul><li><code>${num}</code> &nbsp;&ndash;&nbsp; number of change (0, 1, …)</li><li><code>${rev}</code> &nbsp;&ndash;&nbsp; git revision</li><li><code>${path}</code> &nbsp;&ndash;&nbsp; path of the file being changed</li><li><code>${parent}</code> &nbsp;&ndash;&nbsp; parent git revision</li><li><code>${blob}</code> &nbsp;&ndash;&nbsp; ID of blob object</li><li><code>${parent_blob}</code> &nbsp;&ndash;&nbsp; ID of parent blob object</li><li><code>$convert(${branch},"subStr","newSubStr")</code> &nbsp;&ndash;&nbsp; this inline function returns branch name with **subStr** replaced by a <b>newSubStr</b>. The <code>${branch}</code> supports the character requirements on some hosting services.</li></ul> |
| _**mergeRequestFormat**_ | _String._ Optional.<br><br>This is the URL to display content of pull/merge requests on the git server. Use the following variables:<br><br>`${mergereqId}` &mdash; ID of the pull/merge request |
| _**branchLinkFormat**_ | _String._ Optional.<br><br>This is the URL to display a branch on the git server. Use the following variables:<br><br>`${branch}` – Name of the branch |
| _**commitsValidationRequired**_ | _Boolean._ Read-only.<br><br>This setting is only applicable to self-hosted git servers. For example, you are hosting your git repositories in your own server such as GitLab CE/EE or GitHub Enterprise. If a developer tries to push a commit without the issue key in its message, the push is rejected by the Git Integration for Jira app.<br><br>If this setting is **enabled**, the commit messages are validated according to the following rules:<br><ul><li>The commit message contains at least one issue key.</li><li>The issue key is valid.</li><li>The issue key exists.</li></ul> |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed). |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**trustFolderStat**_ | _Boolean_. Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default setting for Jira Data Center is **false**.<br><br><img src='/wp-content/uploads/bbb-note-20.png' /> If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_. |
| _**refSpecHeads**_ | _Boolean_. Read-only.<br><br>This is a reference to `refs/heads/*` used for fetching. The default value for this field is _**true**_. |
| _**refSpecTags**_ | _Boolean_. Read-only.<br><br>This is a reference to `refs/tags/*` used for fetching. The default value for this field is _**true**_. |
| _**refSpecNotes**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br><img src='/wp-content/uploads/bbb-info-20.png' /> Git notes are not shown…<br><ul><li>when <code>refs/notes</code> are disabled on connecting a repository;</li><li>when a new note comes when <code>refs/notes</code> is disabled.</li></ul> |
| _**refSpecChanges**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |
| _**prHideFilter**_ | _String._ Optional.<br><br>Displays all pull requests for the specific issue, if left blank. Otherwise, set pull requests matching pattern to hide pull requests on issue pages that match the specified regular expression pattern. |
| _**state**_ | Integer. Read-only. This is the indexing state of the nested repository: <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>QUEUED</b>, <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>UPDATED</b>, <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>SCANNING</b>, <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px; font-size: small;'>ERROR</b>. |

&nbsp;

The login credentials are not inherited for nested repositories to interact with external APIs and .git is based on the integration's credentials.

&nbsp;

### Response
Updates the newly changed parameters to the selected repository.

**Example:**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/repository.json`

Request body (JSON) example:

```json
{
  "id": 3,
  "maxMinsToCommitEmail": 1441,
  "gitViewerEnabled": false
}   
```

**Response:**<br>
```json
{
  "id": 3,
  "displayName": "acmecorp",
  "origin": "https://gitlab.com/wileycoyote/acmecorp.git",
  "mainBranch": "master",
  "root": "/jira/home/data/git-plugin/3_acmecorp",
  "realRoot": "3_acmecorp",
  "absoluteRoot": false,
  "disabled": false,
  "enableFetches": true,
  "sendCommitEmails": true,
  "maxMinsToCommitEmail": 1441,
  "global": true,
  "hosted": false,
  "initDate": 1513662080381,
  "lastIndexedDate": 1586232584347,
  "revisionIndexing": true,
  "gitViewerEnabled": false,
  "disableSslVerification": false,
  "smartCommitsEnabled": true,
  "webLinkType": "gitlab",
  "viewFormat": "",
  "changesetFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}",
  "fileAddedFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}#diff-${num}",
  "fileModifiedFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}#diff-${num}",
  "fileDeletedFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}#diff-${num}",
  "mergeRequestFormat": "https://gitlab.com/wileycoyote/acmecorp/merge_requests/${mergereqId}",
  "branchLinkFormat": "https://gitlab.com/wileycoyote/acmecorp/tree/${branch}",  
  "commitsValidationRequired": true,
  "projectMappingIds":[],
  "trackedFolderId": 1,
  "showAllTags": true,
  "sourcesDiffViewEnabled": true,
  "refSpecNotes": true,
  "refSpecChanges": false,
  "trustFolderStat": false
}
```

&nbsp;

### Repository REST APIs

[Retrieve Repository List](/git-integration-for-jira-data-center/retrieve-repository-list-gij-self-managed)

[Add New Repository](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed)

[Enable/disable Existing Repository](/git-integration-for-jira-data-center/enable-disable-existing-repository-API-gij-self-managed)

[Update Existing Repository](/git-integration-for-jira-data-center/update-existing-repository-gij-self-managed)

**Update Existing Nested Repository** (this page)

[Delete Existing Repository](/git-integration-for-jira-data-center/delete-existing-repository-gij-self-managed)

