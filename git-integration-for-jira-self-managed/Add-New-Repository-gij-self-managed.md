---

title: Add New Repository
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Creates new repository from the given settings.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Add New Repository API call.
    </div>
    </div>
</div>
<br>


## Add New Repository

### url
`/rest/gitplugin/1.0/`**repository**

### method
POST

### Parameters

Request body is a _JSON_ structure supporting the following parameters:

| Parameter | Condition |
| :--- | :--- |
| _**displayName**_ | _String_. Optional.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server. |
| _**mainBranch**_ | _String._ Optional.<br><br>The specified branch will intend to organize the Git Commit tab. A commit will not be shown in other branches if it is a part of the main branch. By default, "master" will be used if a main branch is not specified. |
| _**root**_ | _String_. Optional.<br><br>This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira. |
| _**realRoot**_ | _String_. **Optional on existing servers**.<br><br>This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira.<br><br>This field corresponds to the **Repository root** input box in the Advanced setup/Repository settings.<br><br>![](/wp-content/uploads/bbb-info-20.png) The _**realRoot**_ field may refer to an existing repository on a new server. If "root" doesn't exist, this field must be blank.<br><br>![](/wp-content/uploads/bbb-note-20.png) If this field is specified, _**absoluteRoot**_ must also be defined. |
| _**absoluteRoot**_ | _Boolean_. Optional.<br><br>This field corresponds to the **Cloned root location** input field in the Advanced setup/Repository settings.<br><br>If set to **true**, the repository is automatically managed by Git Integration for Jira app (stored in `$JiraHOME`).<br><br>If set to **false**, the repository is manually configured by the Jira administrator.<br><br>![](/wp-content/uploads/bbb-note-20.png) If this field is specified, _**realRoot**_ must also be defined. |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default value for this field is _**false**_. |
| _**enableFetches**_ | _Boolean._ Optional.<br><br>Set to _**true**_ to enable fetches on git repositories hosted on remote servers.<br><br>Set to _**false**_ to enable fetches on git repositories hosted on the same server as Jira. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the _projectMappingIds_ parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**hosted**_ | **Internal field**. Read-only.<br><br>This field will show whether the repository is hosted on Jira or not. |
| _**revisionIndexing**_ | _Boolean_. Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| _**gitViewerEnabled**_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository.  The default setting for this setting is _**enabled**_. <br><br>![](/wp-content/uploads/bbb-alert-20.png) Users must have the **View Development Tools** _project permission_ in order to use this feature. Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed/). |
| _**username**_ | _String_. **Critical for https origins.**<br><br>Set as username for the git host. Leave blank if 2FA is enabled. |
| _**password**_ | _String_. **Critical for https origins.**<br><br>Set as password for the git host. Leave blank if 2FA is enabled. |
| _**pat**_ | _String._ Optional.<br><br>Personal access token. Required, if 2FA is enabled for the git host. |
| _**disableSslVerification**_ | _Boolean._ Optional. Default is _false_.<br><br>The **SSL Verify** setting is set to **Enabled** by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via Manage git repositories ➜ Actions ➜ **Edit repository settings**. |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is _**true**_. |
| _**webLinkType**_ | _String._ Optional.<br><br>Set web link type equivalent to the connected git host. Set web linking formats by referring to [Git Integration for Jira: Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed/). |
| _**viewFormat**_ | _String._ Optional.<br><br>This URL is unused and not being configured for the newly added integration types. |
| _**changesetFormat**_ | _String. Optional._<br><br>This is the URL used to display revision.  <br>Use the following variable: `${rev}`  – git revision |
| _**fileAddedFormat,**_  <br>_**fileModifiedFormat**_,  <br>_**fileDeletedFormat**_ | _String. Optional._<br><br>This is the URL to display content of added, modified or deleted files.<br><br>Use the following variables:<br><ul><li><code>${num}</code> – number of change (0, 1, …)</li><li><code>${rev}</code> – git revision</li><li><code>${path}</code>  –  path of the file being changed</li><li><code>${parent}</code>  –  parent git revision</li><li><code>${blob}</code>  –  ID of blob object</li><li><code>${parent_blob}</code>  –  ID of parent blob object</li><li><code>$convert(${branch},"subStr","newSubStr")</code>  –  this inline function returns branch name with <b>subStr</b> replaced by a <b>newSubStr</b>. The <code>${branch}</code> supports the character requirements on some hosting services.</li></ul> |
| _**mergeRequestFormat**_ | _String._ Optional.<br><br>This is the URL to display content of pull/merge requests on the git server.  Use the following variables:<br><br>*   `${mergereqId}` – ID of the pull/merge request |
| _**branchLinkFormat**_ | _String._ Optional.<br><br>This is the URL to display a branch on the git server. Use the following variables:<br><br>*   `${branch}` – Name of the branch |
| _**commitsValidationRequired**_ | _Boolean._ Optional.<br><br>This setting is only applicable to self-hosted git servers. For example, you are hosting your git repositories in your own server such as GitLab CE/EE or GitHub Enterprise. If a developer tries to push a commit without the issue key in its message, the push is rejected by the Git Integration for Jira app.<br><br>If this setting is **enabled**, the commit messages are validated according to the following rules:<br><ul><li>The commit message contains at least one issue key.</li><li>The issue key is valid.</li><li>The issue key exists.</li></ul> |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed/). |
| _**projectMappingIds**_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository. When you create a new repository and set the field _gitViewerEnabled_ to **true**, at least one project must be associated with it.<br><br>Example: `"projectMappingIds": [10000]` |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**trustFolderStat**_ | _Boolean_. Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Data Center is **false**.<br><br>If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_.<br><br>When adding new repositories, we recommend to leave this setting to **false** _(default)_. You can change this setting later on via Actions ➜ **Edit repository settings** in the Manage repositories page. |
| _**refSpecNotes**_ | _Boolean_. Optional.  <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br>![](/wp-content/uploads/bbb-info-20.png) Git notes are not shown…<br><ul><li>when <code>refs/notes</code> are disabled on connecting a repository;</li><li>when a new note comes when <code>refs/notes</code> is disabled.</li></ul> |
| _**refSpecChanges**_ | _Boolean_. Optional.  <br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |

<br>

### Response

Adds a new repository to the Git Integration for Jira app repository configuration.

* * *

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`.json`

Request body (JSON) example:

```json
{
  "displayName": "MyGitLab-testrepo",
  "origin": "https://github.com/johnsmith/test-repo.git",
  "mainBranch": "master",
  "absoluteRoot": false,
  "disabled": false,
  "enableFetches": true,
  "sendCommitEmails": true,
  "maxMinsToCommitEmail": 1440,
  "global": true,
  "hosted": false,
  "revisionIndexing": true,
  "gitViewerEnabled": true,
  "username": "",
  "password": "",
  "pat": "thisisthepatofyourgithost",
  "disableSslVerification": false,
  "smartCommitsEnabled": true,
  "webLinkType": "",
  "viewFormat": "",
  "changesetFormat": "",
  "fileAddedFormat": "",
  "fileModifiedFormat": "",
  "fileDeletedFormat": "",
  "commitsValidationRequired": true,
  "projectMappingIds": [
  ],
  "showAllTags": true,
  "sourcesDiffViewEnabled": true,
  "limitGitData": true,
  "refSpecNotes": true,
  "refSpecChanges": false,
  "trustFolderStat": true
}
```

**Response:**

```json
Response:
{
  "id": 68,
  "displayName": "MyGitLab-testrepo",
  "origin": "https://github.com/johnsmith/test-repo.git",
  "mainBranch": "master",
  "root": "/opt/jira-home-shared/data/git-plugin/68_test-repo",
  "realRoot": "68_test-repo",
  "absoluteRoot": false,
  "disabled": false,
  "enableFetches": true,
  "sendCommitEmails": true,
  "maxMinsToCommitEmail": 1440,
  "global": true,
  "hosted": false,
  "initDate": 1626069618147,
  "revisionIndexing": true,
  "gitViewerEnabled": true,
  "disableSslVerification": false,
  "smartCommitsEnabled": true,
  "commitsValidationRequired": true,
  "requireUserPat": false,
  "projectMappingIds":[],
  "showAllTags": true,
  "supportsBranchCreationApi": false,
  "sourcesDiffViewEnabled": true,
  "refSpecNotes": true,
  "refSpecChanges": false,
  "trustFolderStat": false
}
```

