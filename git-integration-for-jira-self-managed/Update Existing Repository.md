---

title: Update Existing Repository
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Updates the existing repository from the given settings.

Only Jira admins can perform the Update Repository API call.

|     |     |
| --- | --- |
| **Update Existing Repository** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**repository** |     |
| _**method**_ |     |
| PUT |     |
| _**parameters**_ |     |
| The Request body is a _JSON_ structure similar to the [Add New Repository API](/wiki/spaces/GIJDC/pages/380666393/Add+New+Repository) plus the [id](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380699263/Update+Existing+Repository#id) parameter: |     |
| **Parameter** | **Condition** |
| #### _id_ | Integer. Required.<br><br>This is the ID of the existing repository. For example, `id : 3,`.<br><br>The Update Repository API will look for the repository with `id : 3` and replaces repository properties according to the declared JSON request body structure file. |
| _**displayName**_ | _String._ Optional.<br><br>This is the name that will appear in the Git Integration for Jira app repositories list. |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project.<br><br>For example, you might host your repository on GitHub, Beanstalk or your own server. |
| _**mainBranch**_ | _String._ Optional.<br><br>The specified branch will intend to organize the Git Commit tab. A commit will not be shown in other branches if it is a part of the main branch. By default, "master" will be used if a main branch is not specified. |
| _**root**_ | _String_. Optional.<br><br>This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira. |
| _**realRoot**_ | _String_. **Optional on existing servers**.<br><br>This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira.<br><br>This field corresponds to the **Repository root** input box in the Advanced setup/Repository settings.<br><br>The `realRoot` field may refer to an existing repository on a new server. If "root" doesn't exist, this field must be blank.<br><br>If this field is specified, `absoluteRoot` must also be defined. |
| _**absoluteRoot**_ | _Boolean_. Optional.<br><br>This field corresponds to the **Cloned root location** input field in the Advanced setup/Repository settings.<br><br>If set to **true**, the repository is automatically managed by Git Integration for Jira app (stored in `$JiraHOME`).<br><br>If set to **false**, the repository is manually configured by the Jira administrator.<br><br>If this field is specified, _**realRoot**_ must also be defined. |
| _**disabled**_ | _Boolean._ Optional.<br><br>Set the repository status to updated (enabled) or disabled. If left blank, the default setting for this field is _**false**_. |
| _**enableFetches**_ | _Boolean._ Optional.<br><br>Set to _**true**_ to enable fetches on git repositories hosted on remote servers.<br><br>Set to _**false**_ to enable fetches on git repositories hosted on the same server as Jira. |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. |
| _**maxMinsToCommitEmail**_ | _Integer._ Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |
| _**global**_ | _Boolean._ Optional.<br><br>If set to true, the [_projectMappingIds_](#projectMappingIds) parameter is ignored. Otherwise the `projectMappingIds` parameter value(s) are applied. |
| _**hosted**_ | **Internal field**. Read-only.<br><br>This field will show whether the repository is hosted on Jira or not. |
| _**revisionIndexing**_ | _Boolean._ Optional.<br><br>This setting turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| #### _gitViewerEnabled_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository.  The default setting for this setting is _**enabled**_. Users must have the **View Development Tools** _project permission_ in order to use this feature.  Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser). |
| _**username**_ | _String._ Optional.<br><br>Set as username for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**password**_ | _String._ Optional.<br><br>Set as password for the git host. Leave blank if 2FA is enabled. Otherwise, fill this in if password has changed. |
| _**pat**_ | _String._ Optional.<br><br>This field accepts personal access token from supported git hosts. Fill this in if 2FA is enabled for the git host and if the PAT has changed. |
| _**disableSslVerification**_ | _Boolean._ Optional. Default is _false_.<br><br>The **SSL Verify** setting is set to **Enabled** by default. If set to disabled, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via **Manage git repositories** ➜ _Actions_ ➜ **Edit repository settings**. |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default setting for this field is _**true**_. |
| #### _webLinkType_ | _String._ Optional.<br><br>Set web link type equivalent to the connected git host. Set web linking formats by referring to [Git Integration for Jira: Web linking](/wiki/spaces/GIJDC/pages/1930398212/Web+linking). |
| _**viewFormat**_ | _String._ Optional.<br><br>This URL is unused and not being configured for the newly added integration types. |
| _**changesetFormat**_ | _String._ Optional.<br><br>This is the URL used to display revision.  <br>Use the following variable: `${rev}`  – git revision |
| _**fileAddedFormat,**_  <br>_**fileModifiedFormat**_,  <br>_**fileDeletedFormat**_ | _String._ Optional.<br><br>This is the URL to display content of added, modified or deleted files.  <br>Use the following variables:<br><br>*   `${num}` –  number of change (0, 1, …)<br>    <br>*   `${rev}`  –  git revision<br>    <br>*   `${path}`  –  path of the file being changed<br>    <br>*   `${parent}`  –  parent git revision<br>    <br>*   `${blob}`  –  ID of blob object<br>    <br>*   `${parent_blob}`  –  ID of parent blob object<br>    <br>*   `$convert(${branch},"subStr","newSubStr")`  –  this inline function returns branch name with **subStr** replaced by a **newSubStr**. The `${branch}` supports the character requirements on some hosting services. |
| _**mergeRequestFormat**_ | _String._ Optional.<br><br>This is the URL to display content of pull/merge requests on the git server. Use the following variables:<br><br>*   `${mergereqId}` – ID of the pull/merge request |
| _**branchLinkFormat**_ | _String._ Optional.<br><br>This is the URL to display a branch on the git server. Use the following variables:<br><br>*   `${branch}` – Name of the branch |
| _**commitsValidationRequired**_ | _Boolean._ Optional.<br><br>This setting is only applicable to self-hosted git servers. For example, you are hosting your git repositories in your own server such as GitLab CE/EE or GitHub Enterprise. If a developer tries to push a commit without the issue key in its message, the push is rejected by the Git Integration for Jira app.<br><br>If this setting is **enabled**, the commit messages are validated according to the following rules:<br><br>*   The commit message contains at least one issue key.<br>    <br>*   The issue key is valid.<br>    <br>*   The issue key exists. |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/wiki/spaces/GIJDC/pages/1930399204/Git+tags). |
| #### _projectMappingIds_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository. When you create a new repository and set the field [_gitViewerEnabled_](#gitViewerEnabled) to **true**, at least one project must be associated with it.<br><br>Example: `"projectMappingIds": [10000]` |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**trustFolderStat**_ | _Boolean_. Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default setting for Jira Data Center is **false**.<br><br>If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_. |
| _**refSpecNotes**_ | _Boolean_. Optional.  <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br>Git notes are not shown…<br><br>*   when `refs/notes` are disabled on connecting a repository;<br>    <br>*   when a new note comes when `refs/notes` is disabled. |
| _**refSpecChanges**_ | _Boolean_. Optional.  <br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |
| _**response**_ |     |
| Updates the newly changed parameters to the selected repository. |     |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`.json`<br><br>Request body (JSON) example:<br><br>```java<br>{<br>  "id": 3,<br>  "maxMinsToCommitEmail": 1441,<br>  "gitViewerEnabled": false<br>}<br>``` |

|     |
| --- |
| **Response:** |
| ```java<br>{<br>  "id": 3,<br>  "displayName": "acmecorp",<br>  "origin": "https://gitlab.com/wileycoyote/acmecorp.git",<br>  "mainBranch": "master",<br>  "root": "/jira/home/data/git-plugin/3_acmecorp",<br>  "realRoot": "3_acmecorp",<br>  "absoluteRoot": false,<br>  "disabled": false,<br>  "enableFetches": true,<br>  "sendCommitEmails": true,<br>  "maxMinsToCommitEmail": 1441,<br>  "global": true,<br>  "hosted": false,<br>  "initDate": 1513662080381,<br>  "lastIndexedDate": 1586232584347,<br>  "revisionIndexing": true,<br>  "gitViewerEnabled": false,<br>  "disableSslVerification": false,<br>  "smartCommitsEnabled": true,<br>  "webLinkType": "gitlab",<br>  "viewFormat": "",<br>  "changesetFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}",<br>  "fileAddedFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}#diff-${num}",<br>  "fileModifiedFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}#diff-${num}",<br>  "fileDeletedFormat": "https://gitlab.com/wileycoyote/acmecorp/commit/${rev}#diff-${num}",<br>  "mergeRequestFormat": "https://gitlab.com/wileycoyote/acmecorp/merge_requests/${mergereqId}",<br>  "branchLinkFormat": "https://gitlab.com/wileycoyote/acmecorp/tree/${branch}",  <br>  "commitsValidationRequired": true,<br>  "projectMappingIds":[],<br>  "trackedFolderId": 1,<br>  "showAllTags": true,<br>  "sourcesDiffViewEnabled": true,<br>  "refSpecNotes": true,<br>  "refSpecChanges": false,<br>  "trustFolderStat": false<br>}<br>``` |

### Related articles

*   Page:

    [Retrieve Repository List](/wiki/spaces/GIJDC/pages/380666386/Retrieve+Repository+List) (Git Integration for Jira Data Center)

*   Page:

    [Add New Repository](/wiki/spaces/GIJDC/pages/380666393/Add+New+Repository) (Git Integration for Jira Data Center)

*   Page:

    [Update Existing Repository](/wiki/spaces/GIJDC/pages/380699263/Update+Existing+Repository) (Git Integration for Jira Data Center)

*   Page:

    [Delete Existing Repository](/wiki/spaces/GIJDC/pages/380797296/Delete+Existing+Repository) (Git Integration for Jira Data Center)