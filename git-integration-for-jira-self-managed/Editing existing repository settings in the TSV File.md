---

title: Editing existing repository settings in the TSV File
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Navigate to the .tsv file and edit it with your favorite spreadsheet program.

[**Google Drive**](http://drive.google.com/) is also a recommended place to edit the .tsv file.

Populate/edit the fields by utilizing the following options:

|     |     |     |
| --- | --- | --- |
| **Column/Field** | **Description** |     |     |
| _**id**_ | _Integer_. Required.<br><br>Assign an ID number to a repository.<br><br>This field is required if you wish to update or edit existing repositories by setting this value to their equivalent IDs. Otherwise, if this field is left blank, the repository will be created as new.<br><br>**Important!**  <br>When importing to a new server, the _**id**_ field must be blank. |     |     |
| _**realRoot**_ | _String_. **Optional on existing servers**.<br><br>This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira.<br><br>The `realRoot` field may refer to an existing repository on a new server. If `root` doesn't exist, this field must be blank. |     |     |
| _**absoluteRoot**_ | _Boolean_. Optional.<br><br>This field corresponds to the _**Cloned root location**_ input field in the Advanced setup/Repository settings.<br><br>If this field is set to `true`, the repository is automatically managed by Git Integration for Jira app (stored in `$JiraHOME`). If set to `false`, the repository is manually configured by the Jira administrator.<br><br>If this field is specified, `realRoot` must also be defined. |     |     |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project. For example, you might host your repository on GitHub, Beanstalk or your own server.<br><br>SSH INTEGRATION Before adding repositories (new or existing) via Bulk change, make sure that you have added SSH keys for the respective git hosts in the Git Integration for Jira app configuration page. BigBrassBand recommends to use the `git@<url>:[your-git-repo].git` format for the repository origin URL and [adding of SSH Keys](/wiki/spaces/GIJDC/pages/1930396698/Adding+a+private+SSH+key) for each git host in the Git Integration for Jira app configuration page.<br><br>HTTPS/HTTP INTEGRATION For HTTPS git repositories, obtain the URL from your git host. If you use HTTP/HTTPS URLs in the origin field, the Git Integration for Jira app will not be able to import said repositories due to missing credentials. Entering repository login credentials in the TSV file is not advisable due to a possible security risk. Therefore, when editing the _**origin**_ field of the TSV file, enter value using the `git@<repository-url>:[your-git-repo].git` format. This format will use the SSH key(s) from the Git Integration for Jira app configuration instead.<br><br>The repository origin may not be hosted on the same server as Jira. |     |     |
| _**displayName**_ | _String_. Optional.<br><br>Define a meaningful name for this repository configuration. This is the name that will appear in the Git Integration for Jira app repositories list. If this field is left blank, the default value is obtained from the origin. |     |     |
| _**enableFetches**_ | _Boolean._ Optional.<br><br>Set to `true` to enable fetches on git repositories hosted on remote servers. In this mode, fetches are enabled using any external source. The reindex background service will initiate the fetch then add the new commits to the plugin index.<br><br>Set to `false` to enable fetches on git repositories hosted on the same server as Jira. Fetches are enabled when the repository is hosted locally. In this mode, no fetches are made. The reindex service runs in the background and process every new commit found. |     |     |
| _**revisionIndexing**_ | _Boolean_. Optional.<br><br>The default value for this field is `true`.<br><br>This option turns on the memory cache which is used when list of commits are displayed. Set to `true` if revision indexing will index and link to any mentioned issue keys in the revision history or not (`false`). |     |     |
| _**mainBranch**_ | _String._ Optional.<br><br>Set specific branch as the main branch for this repository. A commit will not be shown in other branches if it is a part of the main branch. By default, `master` will be used if a main branch is not specified.<br><br>**Default Main Branch**  <br>Most git integrations allow changing of the default branch of the repository/project other than `master` at the server level. On each reindex, this change is reflected in the Repository Settings. In the case of Gerrit, the default main branch is always `master`. |     |     |
| _**username, password**_ | _String_. Optional.<br><br>Critical for https origins. Define `username` and `password` for the git host. Leave blank if 2FA is enabled in your git host. |     |     |
| _**pat**_ | _String_. Optional.<br><br>Required, if 2FA is enabled for the git host. This field accepts personal access token from supported git hosts. |     |     |
| #### _gitViewerEnabled_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository. The default setting for this field is `enabled`.<br><br>Users must have the **View Development Tools** _project permission_ in order to use this feature. Consult your Jira System Administrator on permissions.<br><br>For more information, see [Documentation -- Repository Browser](/git-integration-for-jira-self-managed/Repository-Browser). |     |     |
| #### _projectMapping_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository.<br><br>*   This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored _(equivalent to unchecking the **Associate to All Projects** checkbox)_.  <br>    _Example:_ `10000,10100`<br>    <br>*   If you change an existing repository, leaving this field blank will use the existing values of the repository configuration.<br>    <br>*   Setting this field to `ALL` will retain _**projectMapping**_ settings and sets the "All Projects" flag to `true` _(equivalent to checking the_ **Associate to All Projects** _checkbox)_.<br>    <br><br>If projects are not associated to the repository, you must leave this field blank and set the _**gitViewerEnabled**_ field to `false`. |     |     |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is `true`. |     |     |
| _**sendCommitEmails**_ | _Boolean._ Optional.<br><br>Enables or disables commit notification emails for this repository. If left blank, the default value for this field is `true`. |     |     |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |     |     |
| _**changesetFormat, fileAddedFormat, fileModifiedFormat, fileDeletedFormat**_ | _String._ Optional.<br><br>This is the URL to display content of added, modified or deleted files. Use the following variables:<br><br>*   `${num}` –  number of change (0, 1, …)<br>    <br>*   `${rev}`  –  git revision<br>    <br>*   `${path}`  –  path of the file being changed<br>    <br>*   `${parent}`  –  parent git revision<br>    <br>*   `${blob}`  –  ID of blob object<br>    <br>*   `${parent_blob}`  –  ID of parent blob object<br>    <br>*   `$convert(${branch},"subStr","newSubStr")`  –  this inline function returns branch name with _subStr_ replaced by a _newSubStr_. As of **v2.11.0+** of the Git Integration app, the `${branch}` code has been changed to cope up with the character requirements on some hosting services. |     |     |
| _**disabled**_ | _Boolean_. Optional.<br><br>Add this repository into the Git Integration app configuration and set its status to updated (_enabled_) or disabled. If left blank, the default value for this field is `false`. |     |     |
| _**hosted**_ | _Boolean._ Optional.<br><br>**Internal field**. Read-only. This field will show whether the repository is hosted on Jira or not. |     |     |
| _**tagsFilter**_ | _String._ Optional.<br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>Set _**tagsFilter**_ with a valid Java regular expression or an empty string. The filtered tags are displayed on the Jira Developer Panel.<br><br>For more information, see example in [Documentation -- Git tags](/git-integration-for-jira-self-managed/Git-tags). |     |     |
| _**requireUserPat**_ | _Boolean_. Optional.<br><br>Setting this field to `true` will require users to specify their own PAT for branch and pull/merge request management. If left blank, the default value of this field is `false`. |     |     |
| _**integrationType**_ | _Boolean._ **Internal field**.<br><br>This field will show whether the repository is a tracked folder, a connected GitLab server or a simple repository. |     |     |
| _**trackedFolderId**_ | _Integer._ **Internal field**.<br><br>This field will display the ID of the "parent" repository. It can be changed in order to convert the repository to a sub-repository.<br><br>**Use with caution**<br><br>If the modified sub-repository is not located in the tracked folder, it will be removed by the sequential auto-reindex. |     |     |
| _**delete**_ | _Flag_. Optional.<br><br>Set **"delete"** on this column/field as a confirmation to the Git Integration app to automatically remove the selected repository from the plugin configuration. If left blank, no changes will occur. |     |     |
| _**sshKeyId**_ | _Integer_. Optional.<br><br>This is the ID of an associated SSH key. |     |     |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |     |     |
| _**limitGitData**_ | The Limit commits feature is deprecated after January 1, 2021.  From then on, all commits will be limited by project permissions.<br><br>_Boolean._ Optional.<br><br>Enables/disables limitation of commits shown in Git Commits issue tab, Git Commits page and all across the Git Integration for Jira app by project association. This only applies when project associations are set (`projectMapping`).<br><br>When `limitGitData` is set to `true` for a git repository and there are project associations set (`projectMapping`) — The git data is not shown from that repository in any project except those from _**projectMapping**_.<br><br>Unless the issue is from a project association list in `projectMapping`, some data are not shown such as:<br><br>*   Commits, branches and tags in the **Issue sidebar**.<br>    <br>*   Commits in **Git Commits tab**.<br>    <br>*   Commits in **Git Commits page**.<br>    <br>*   Commits and branches in **Git Roll Up tab**.<br>    <br>*   Commits in **Project/Issue** pages.<br>    <br>*   Commits in **Compare pages**. User read/view permission restriction also applies.<br>    <br><br>_**limitGitData**_ defaults to `true` when setting new project associations.<br><br>_**limitGitData**_ **Upgrade and installation defaults:** |     |     |
| **Condition** | **Repository** | **Result** |
| _Upgrade to new add-on version_ | Has several repositories with project associations | Defaults to _**false**_ because there is no sudden change in behavior |
| _Upgrade to new add-on version_ | Adds a new repository and set project associations | Defaults to _**true**_ because it is a new repository |
| _Installs add-on for the first time_ | Adds a new repository and set project associations | Defaults to _**true**_ because it is a new repository |
| _**apiPath**_ | _String_. Optional.<br><br>The integration will use this relative REST API path starting with "/" to retrieve the list of tracked repositories.<br><br>For more information, see [Working with Custom API Path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path). |     |     |
| _**apiFilter**_ | _String_. Optional.<br><br>JMESPath filter expression will be used to filter API results.<br><br>See our [Integration Guides](/git-integration-for-jira-self-managed/Integration-Guides), [Working with JMESPath filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters) or [contact support](mailto:support@bigbrassband.com) for help writing expressions. |     |     |
| _**tfsCollection**_ | _String_. Optional. TFS or Azure DevOps Server integrations only.<br><br>A TFS collection is a group of TFS team projects. Specify an existing TFS Collection for use with Jira integration. |     |     |
| _**awsRegion**_ | _String_. Optional. AWS integrations only.<br><br>Specify AWS region; where CodeCommit repositories are located. The list of regions with their names can be found [**here**](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).<br><br>Git Integration for Jira app supported regions:<br><br>*   us-east-1<br>    <br>*   us-east-2<br>    <br>*   us-west-1<br>    <br>*   us-west-2<br>    <br>*   ap-south-1<br>    <br>*   ap-northeast-2<br>    <br>*   ap-southeast-1<br>    <br>*   ap-southeast-2<br>    <br>*   ap-northeast-1<br>    <br>*   ca-central-1<br>    <br>*   eu-central-1<br>    <br>*   eu-west-1<br>    <br>*   eu-west-2<br>    <br>*   eu-west-3<br>    <br>*   eu-north-1<br>    <br>*   me-south-1<br>    <br>*   sa-east-1 |     |     |
| _**sslVerify**_ | _Boolean_. Optional.<br><br>Default is `TRUE`. The **SSL Verify** option is set to enabled by default. If set to `FALSE`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via menu Git ➜ Manage repositories ➜ _Actions_ ➜ **Edit repository/integration settings**. |     |     |
| _**trustFolderStat**_ | When this field is set to `false`, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to `true`, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Server is `true`.<br><br>The _default_ value for Jira Data Center is `false`.<br><br>If your repository is stored on a network share, it is highly recommended to set this field to `false`. |     |     |
| _**weblinkType**_ | _String._ Optional.<br><br>Set web link type equivalent to the connected git host. Set web linking formats by referring to [Documentation – Web linking](/git-integration-for-jira-self-managed/Web-linking). |     |     |
| _**viewFormat**_ | _String._ Optional.<br><br>This is the URL to display diff from some git hosts. Other git hosts does not use this field. |     |     |
| _**mergeRequestFormat**_ | _String._ Optional.<br><br>This is the URL to display content of pull/merge requests on the git server.  Use the following variables:<br><br>*   `${mergereqId}` – ID of the pull/merge request |     |     |
| _**branchLinkFormat**_ | _String._ Optional.<br><br>This is the URL to display a branch on the git server. Use the following variables:<br><br>*   `${branch}` – Name of the branch |     |     |
| _**refSpecNotes**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is `false`.<br><br>Git notes are not shown…<br><br>*   when `refs/notes` are disabled on connecting a repository;<br>    <br>*   when a new note comes when `refs/notes` is disabled. |     |     |
| _**refSpecChanges**_ | _Boolean_. Optional.<br><br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is `false`. |     |     |
| _**refSpecCustom**_ | _String_. Optional.<br><br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |     |     |

Take note that the .tsv file is verified by the Git for Jira app with the following rules:

*   The header row is required.

*   The order of fields specified in the header row – is the order of the fields in the following rows.

*   If a field is omitted from the header row, the Git Integration app will use the default value for a new repository. The Git Integration app will keep the current value of a repository if it already exists in the configured repositories.

*   If a repository is not listed in the .tsv file, no changes will be made if the same repository exists in the add-on configuration.


Save the file to a tab-delimited format:

*   **OSX users** – select all data in Numbers and then paste into a text editor and save. Name the file with the **.tsv** extension (_repo-example-00.tsv_).

*   **Excel users** – save the file as **Text (Tab delimited) (\*.txt)**. Rename file's **.txt** extension to **.tsv**.

*   **Google Drive** - upload the file to this service. Right click the **.tsv** file then open it with _Google Sheets_.  Make the necessary changes then go to File ➜ Download as ➜ **Tab separated values (.tsv)** to your local machine.


[« Add new repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397912/Import+new+repositories+via+Bulk+change)

[Removing existing repositories via Bulk change »](/wiki/spaces/GIJDC/pages/1930397978/Removing+existing+repositories+via+Bulk+change)

### More related topics about bulk change

*   Page:

    [Bulk change](/git-integration-for-jira-self-managed/Bulk-change) (Git Integration for Jira Data Center)

*   Page:

    [Exporting repository configuration via Bulk change](/wiki/spaces/GIJDC/pages/1930397830/Exporting+repository+configuration+via+Bulk+change) (Git Integration for Jira Data Center)

*   Page:

    [Requirement for secured import](/wiki/spaces/GIJDC/pages/1930397869/Requirement+for+secured+import) (Git Integration for Jira Data Center)

*   Page:

    [Import existing repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397888/Import+existing+repositories+via+Bulk+change) (Git Integration for Jira Data Center)

*   Page:

    [Import new repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397912/Import+new+repositories+via+Bulk+change) (Git Integration for Jira Data Center)

*   Page:

    [Editing existing repository settings in the TSV File](/wiki/spaces/GIJDC/pages/1930397941/Editing+existing+repository+settings+in+the+TSV+File) (Git Integration for Jira Data Center)

*   Page:

    [Removing existing repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397978/Removing+existing+repositories+via+Bulk+change) (Git Integration for Jira Data Center)