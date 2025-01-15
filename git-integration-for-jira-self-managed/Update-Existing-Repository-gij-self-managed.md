---

title: Update Existing Repository API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Updates the existing repository from the given settings.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Update Repository API call.
    </div>
    </div>
</div>

### url
`{JiraBaseURL}/rest/gitplugin/1.0/repository`

### method
PUT

### Parameters

The Request body is a _JSON_ structure similar to the [Add New Repository API](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed) plus the _**id**_ parameter:

| Field | Description |
| :--- | :--- |
| _**id**_ | Integer. Required.<br><br>This is the ID of the existing repository. For example, `id : 3,`.<br><br>The Update Repository API will look for the repository with `id : 3` and replaces repository properties according to the declared JSON request body structure file. |
| _**displayName**_ | _String._ Optional.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server. |
| _**mainBranch**_ | _String._ Optional.<br><br>The specified branch will intend to organize the Git Commit tab. A commit will not be shown in other branches if it is a part of the main branch. By default, "master" will be used if a main branch is not specified. |
| _**realRoot**_ | _String_. Required.<br><br>This is the local path to the repository on the server where your Jira service is running. It contains absolute path or relative path depending on `absoluteRoot`.<br><br>This field corresponds to the **Repository root** input box in the Advanced setup/Repository settings.<br><br>![](/wp-content/uploads/bbb-alert-20.png) If this field is specified, `absoluteRoot` must also be defined. |
| _**absoluteRoot**_ | _Boolean_. Required.<br><br>This field shows whether `realRoot` is a relative path or absolute path.<br><br>If set to _**false**_, the `realRoot` is a path relative to `${JiraHOME}/data/git-plugin` folder.<br><br>This field corresponds to the **Cloned root** location input field in the Advanced setup/Repository settings.<br><br>Repositories located in `${JiraHOME}/data/git-plugin` folder are automatically managed by the Git Integration for Jira app.<br><br>![](/wp-content/uploads/bbb-note-20.png) If this field is specified, `realRoot` must also be defined. |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default setting for this field is _**false**_.<br><br><b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>UPDATE</b> <br>There has been a change to the API behavior, so disabling a repository using this field now could return a success message, whereas its actual state remains enabled.<br><br>To workaround this issue, use the request format below:<br>`curl --location --request PUT 'https://{JIRA_BASE_URL}/rest/gitplugin/1.0/repository/{REPO_ID}/disable?disable=true' --header 'Content-Type: application/json'` |
| _**enableFetches**_ | _Boolean._ Optional.<br><br>Set to _**true**_ to enable fetches on git repositories hosted on remote servers.<br><br>Set to _**false**_ to enable fetches on git repositories hosted on the same server as Jira. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer._ Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the _projectMappingIds_ parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**hosted**_ | **Internal field**. Read-only.<br><br>This field will show whether the repository is hosted on Jira or not. |
| _**revisionIndexing**_ | _Boolean._ Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| **_gitViewerEnabled_** | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository.  The default setting for this setting is _**enabled**_. Users must have the **View Development Tools** _project permission_ in order to use this feature.  Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed). |
| _**username**_ | _String._ Optional.<br><br>Set as username for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**password**_ | _String._ Optional.<br><br>Set as password for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**pat**_ | _String._ Optional.<br><br>This field accepts personal access token from supported git hosts. Fill this in if 2FA is enabled for the git host and if the PAT has changed. |
| _**disableSslVerification**_ | _Boolean._ Optional. Default is _false_.<br><br>The **SSL Verify** setting is set to **Enabled** by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via **Manage git repositories** ➜ _Actions_ ➜ **Edit repository settings**. |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default setting for this field is _**true**_. |
| _**webLinkType**_ | _String._ Optional.<br><br>Set web link type equivalent to the connected git host. Set web linking formats by referring to [Git Integration for Jira: Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed). |
| _**viewFormat**_ | _String._ Optional.<br><br>This URL is unused and not being configured for the newly added integration types. |
| _**changesetFormat**_ | _String._ Optional.<br><br>This is the URL used to display revision.<br><br>Use the following variable: `${rev}`  – git revision |
| _**fileAddedFormat,**_  <br>_**fileModifiedFormat**_,  <br>_**fileDeletedFormat**_ | _String._ Optional.<br><br>This is the URL to display content of added, modified or deleted files.  <br>Use the following variables:<br><ul><li><code>${num}</code> –  number of change (0, 1, …)</li><li><code>${rev}</code>  –  git revision</li><li><code>${path}</code>  –  path of the file being changed</li><li><code>${parent}</code>  –  parent git revision</li><li><code>${blob}</code>  –  ID of blob object</li><li><code>${parent_blob}</code>  –  ID of parent blob object</li><li><code>$convert(${branch},"subStr","newSubStr")</code>  –  this inline function returns branch name with **subStr** replaced by a <b>newSubStr</b>. The <code>${branch}</code> supports the character requirements on some hosting services.</li></ul> |
| _**mergeRequestFormat**_ | _String._ Optional.<br><br>This is the URL to display content of pull/merge requests on the git server. Use the following variables:<br><br>`${mergereqId}` – ID of the pull/merge request |
| _**branchLinkFormat**_ | _String._ Optional.<br><br>This is the URL to display a branch on the git server. Use the following variables:<br><br>`${branch}` – Name of the branch |
| _**commitsValidationRequired**_ | _Boolean._ Optional.<br><br>This setting is only applicable to self-hosted git servers. For example, you are hosting your git repositories in your own server such as GitLab CE/EE or GitHub Enterprise. If a developer tries to push a commit without the issue key in its message, the push is rejected by the Git Integration for Jira app.<br><br>If this setting is **enabled**, the commit messages are validated according to the following rules:<br><ul><li>The commit message contains at least one issue key.</li><li>The issue key is valid.</li><li>The issue key exists.</li></ul> |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed). |
| _**projectMappingIds**_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository. When you create a new repository and set the field _gitViewerEnabled_ to **true**, at least one project must be associated with it.<br><br>Example: `"projectMappingIds": [10000]` |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**trustFolderStat**_ | _Boolean_. Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default setting for Jira Data Center is **false**.<br><br><img src='/wp-content/uploads/bbb-note-20.png' /> If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_. |
| _**refSpecNotes**_ | _Boolean_. Optional.  <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br><img src='/wp-content/uploads/bbb-info-20.png' /> Git notes are not shown…<br><ul><li>when <code>refs/notes</code> are disabled on connecting a repository;</li><li>when a new note comes when <code>refs/notes</code> is disabled.</li></ul> |
| _**refSpecChanges**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |
| _**prHideFilter**_ | _String_. Optional. <br>Displays all pull requests for the specific issue, if left blank. Otherwise, set pull requests matching pattern to hide pull requests on issue pages that match the specified regular expression pattern. |

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

**Update Existing Repository** (this page)

[Delete Existing Repository](/git-integration-for-jira-data-center/delete-existing-repository-gij-self-managed)

```java
curl --location --request PUT 'https://agile.corp.edp.pt/rest/gitplugin/1.0/repository/16624/disable?disable=true'
--header 'Content-Type: application/json'
--header 'Authorization: ••••••'
--header 'Cookie: +++++'
```