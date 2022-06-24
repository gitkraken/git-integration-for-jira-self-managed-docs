---

title: Bulk Export
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The API returns a file with the plugin configuration.

Only Jira admins can perform the Bulk Export API call.

## Bulk Export Configuration

_**url**_ - `/rest/gitplugin/1.0/`**configuration**

_**method**_ - GET

_**parameters**_ - none

_**response**_

Generates a tab-separated values (.tsv) file. See the parameters table below for more information on each parameter in a TSV file.

_**Download sample file**_ - [**configuration\_get.py**](https://bigbrassband.com/files/configuration_get.zip)

**Example:**

```java
Usage:
user@home:~$ python configuration_get.py > conf.tsv
```

Edit the TSV file by referring to the parameters below:

| **Column/Field** | **Description** |
| --- | --- |
| _**id**_ | _Integer_. Required.<br><br>Assign an ID number to a repository. This is required if you wish to update or edit existing repositories by setting this value to their equivalent IDs. If this field is left blank, the repository will be created as new.<br><br>When importing to a new server, the `id` field must be blank. |
| _**realRoot**_ | _String_. **Optional on existing servers**.<br><br>This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira.<br><br>This field corresponds to the **Repository root** input box in the Advanced setup/Repository settings.<br><br>The `realRoot` field may refer to an existing repository on a new server. If "root" doesn't exist, this field must be blank.<br><br>If this field is specified, `absoluteRoot` must also be defined. |
| _**absoluteRoot**_ | _Boolean_. Optional.<br><br>This field corresponds to the **Cloned root location** input field in the Advanced setup/Repository settings.<br><br>If set to **true**, the repository is automatically managed by Git Integration for Jira app (stored in `$JiraHOME`).<br><br>If set to **false**, the repository is manually configured by the Jira administrator.<br><br>If this field is specified, _**realRoot**_ must also be defined. |
| _**origin**_ | _String_. Required.<br><br>This is the URL to the hosted git service used on the project. For example, you might host your repository on GitHub, Beanstalk or your own server.<br><br>BigBrassBand recommends to use the `git@<url>:[your-git-repo].git` format for the repository origin URL and adding of SSH Keys for each git host in the Git Integration app configuration page.<br><br>For HTTPS git repositories, obtain the URL from your git host then set your login credentials in the `username` and `password` (or `pat`) field to connect to them.<br><br>The repository origin may not be hosted on the same server as Jira. |
| _**displayName**_ | _String._ Optional. Some git hosts may require this to be filled in.<br><br>Define a meaningful name for this repository configuration. If this field is left blank, the default value is obtained from the origin. |
| _**enableFetches**_ | _Boolean_. Optional.<br><br>Set to **true** to enable fetches on git repositories hosted on remote servers.<br><br>Set to **false** to enable fetches on git repositories hosted on the same server as Jira.<br><br>See section [_Enable Fetches_](/git-integration-for-jira-self-managed/connecting-a-repository-via-advanced-setup-gij-self-managed#enable-fetches/) in Connecting a repository via Advanced setup. The default boolean value for this field is **true**. |
| _**revisionIndexing**_ | _Boolean_. Optional. <br><br>The default boolean value for this field is **true**.<br><br>This option turns on the memory cache which is used when list of commits are displayed. Set to _**true**_ if revision indexing will index and link to any mentioned issue keys in the revision history or not (_**false**_). |
| **mainBranch** | _String_. Optional.<br><br>Set specific branch as the main branch for this repository. The default value is "master".<br><br>See section [_Main Branch_](/git-integration-for-jira-self-managed/connecting-a-repository-via-advanced-setup-gij-self-managed#main-branch) in Connecting a repository via Advanced setup. |
| _**username, password**_ | _String_. Optional.<br><br>Leave blank if 2FA is enabled for the git host. |
| _**pat**_ | _String_. Optional.<br><br>Required, if 2FA is enabled for the git host. This field accepts personal access token from supported git hosts. |
| _gitViewerEnabled_ | _Boolean._ Optional.<br><br>Enables or disables the **Repository Browser** feature for this repository. The default setting for this option is _**enabled**_.<br><br>Users must have the **View Development Tools** _project permission_ in order to use this feature. Consult your Jira System Administrator on permissions.<br><br>For more information, see section, [Repository Browser](/git-integration-for-jira-self-managed/repository-browser-gij-self-managed). |
| _projectMapping_ | _Long \[ \]_. Array. Optional.<br><br>These are numeric projects IDs associated with the repository.<br><ul><li>This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored (<i>equivalent to unchecking the **Associate to All Projects** checkbox in the Advanced Setup dialog</i>). <b>Example:</b> <code>10000,10100</code></li><li>If you change an existing repository, leaving this field blank will use the existing values of the repository configuration.</li><li>Setting this field to **ALL** will retain <code>projectMapping</code> settings and sets "All Projects" flag to true (<i>equivalent to checking the **Associate to All Projects** checkbox in the Advanced Setup dialog</i>).</li></ul>If projects are not associated to the repository, you must leave this field blank and set the _gitViewerEnable_ field to **false**. |
| _**smartCommitsEnabled**_ | _Boolean._ Optional.<br><br>This setting is enabled by default. Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is _**true**_. |
| _**sendCommitEmails**_ | _Boolean_. Optional.<br><br>Send commit notification emails for this repository. If left blank, the default value for this field is **true**. |
| _**maxMinsToCommitEmail**_ | _Integer_. Optional.<br><br>Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. Default value is **1440** minutes. |
| _webLinkType_ | _String._ Optional.<br><br>Set web link type equivalent to the connected git host. Set web linking formats by referring to [Git Integration for Jira: Web linking](/git-integration-for-jira-self-managed/web-linking-gij-self-managed). |
| _**viewFormat**_ | _String._ Optional.<br><br>This URL is unused and not being configured for the newly added integration types. |
| _**changesetFormat**_ | _String_. Optional.<br><br>This is the URL used to display revision.  <br>Use the following variable: `${rev}`  – git revision |
| _**fileAddedFormat, fileModifiedFormat, fileDeletedFormat**_ | _String_. Optional.<br><br>This is the URL to display content of added, modified or deleted files.  <br>Use the following variables:<br><ul><li><code>${num}</code> –  number of change (0, 1, …)</li><li><code>${rev}</code>  –  git revision</li><li><code>${path}</code>  –  path of the file being changed</li><li><code>${parent}</code>  –  parent git revision</li><li><code>${blob}</code>  –  ID of blob object</li><li><code>${parent_blob}</code>  –  ID of parent blob object</li><li><code>$convert(${branch},"subStr","newSubStr")</code>  –  this inline function returns branch name with subStr replaced by a newSubStr. The `${branch}` supports the character requirements on some hosting services.</li></ul> |
| _**mergeRequestFormat**_ | _String._ Optional.<br><br>This is the URL to display content of pull/merge requests on the git server.  Use the following variables:<br><br>`${mergereqId}` – ID of the pull/merge request |
| _**branchLinkFormat**_ | _String._ Optional.<br><br>This is the URL to display a branch on the git server.  Use the following variables:<br><br>`${branch}` – Name of the branch |
| _**disabled**_ | _Boolean_. Optional.<br><br>Add this repository into the Git Integration app configuration and set its status to updated (_enabled_) or disabled. If left blank, the default value for this field is **false**. |
| _**hosted**_ | **Internal field**. Read-only.<br><br>This field will show whether the repository is hosted on Jira or not. |
| _**tagsFilter**_ | _String_. Optional. <br><br>Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.<br><br>For more information, see example in [Show tags](/git-integration-for-jira-self-managed/git-tags-gij-self-managed).<br><br>Set `tagsFilter` with a valid Java regular expression or an empty string. The filtered tags are displayed on the Jira Developer Panel. |
| _**integrationType**_ | _Flag_. **Internal field**.<br><br>This field will show whether the repository is a tracked folder, a connected git service or a simple repository. |
| _**trackedFolderId**_ | _Integer_. **Internal field**.<br><br>This field will display the ID of the "parent" repository. It can be changed in order to convert the repository to a sub-repository.<br><br>**Use with caution**  <br>If the modified sub-repository is not located in the tracked folder, it will be removed by the sequential auto-reindex. |
| _**delete**_ | _String_. Optional.<br><br>Enter "delete" on this column/field as a confirmation to the Git Integration app to automatically remove the selected repository from the plugin configuration. If left blank, no changes will occur. |
| _**sshKeyId**_ | _Integer_. Optional.<br><br>This is the ID of an associated SSH key. |
| _**requireUserPat**_ | _Boolean_. Optional.<br><br>Setting this parameter to _**true**_ will require users to specify their own PAT for branch and pull/merge request management. |
| _**sourcesDiffViewEnabled**_ | _Boolean._ Optional.<br><br>When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira. |
| _**sslVerify**_ | Boolean. Optional.<br><br>Default is **true**. The SSL Verify option is set to `Enabled` by default. If set to **false**, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.<br><br>This setting can also be accessed via Manage git repositories ➜  <br>_Actions_ ➜ **Edit integration/repository settings**. |
| _**apiPath**_ | _String_. Optional.<br><br>The integration will use this relative REST API path starting with "/" to retrieve the list of tracked repositories. For more information, see article [Working with Custom API path](/git-integration-for-jira-self-managed/working-with-custom-api-path-gij-self-managed). |
| _**apiFilter**_ | _String_. Optional.<br><br>JMESPath filter expression will be used to filter API results. See article [Working with JMESPath filters](/git-integration-for-jira-self-managed/working-with-jmespath-filters-gij-self-managed) or [contact support](mailto:support@bigbrassband.com) for help writing expressions. |
| **tfsCollection** | _String_. Optional. TFS or Azure DevOps Server integrations only.<br><br>A TFS collection is a group of TFS team projects. Specify an existing TFS Collection for use with Jira integration. |
| _**awsRegion**_ | _String_. Optional. AWS integrations only.<br><br>Specify a region for AWS CodeCommit integration. For region values, see [**AWS Regions and Endpoints**](https://docs.aws.amazon.com/general/latest/gr/rande.html). |
| _**trustFolderStat**_ | _Boolean._ Optional.<br><br>When the `trustFolderStat` setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.<br><br>The default value for Jira Data Center is **false**.<br><br>If your repository is stored on a network share, it is highly recommended to set the `trustFolderStat` value to _**false**_.<br><br>When adding new repositories, we recommend to leave the setting of the `trustFolderStat`value to **false** _(default)_. You can change this setting later on via _Actions_ ➜ _**Edit repository settings**_ in the Manage repositories page. |
| _**refSpecNotes**_ | _Boolean_. Optional.  <br>This is a reference to `refs/notes/*` used for fetching. The default value for this field is _**true**_.<br><br>Git notes are not shown…<br><ul><li>when <code>refs/notes</code> are disabled on connecting a repository;</li><li>when a new note comes when <code>refs/notes</code> is disabled.</li></ul> |
| _**refSpecChanges**_ | _Boolean_. Optional.  <br>This is a reference to `refs/changes/*` used for fetching. The default value for this field is _**false**_. |
| _**refSpecCustom**_ | _String_. Optional.  <br>This is a user-defined list of references used for fetching. It is a comma-separated list with the format: `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ... |

Take note that the .tsv file is verified by the Git Integration for Jira app with the following rules:

*   The header row is required.

*   The order of fields specified in the header row – is the order of the fields in the following rows.

*   If a field is omitted from the header row, the Git Integration app will use the default value for a new repository. The Git Integration app will keep the current value of a repository if it already exists in the configured repositories.

*   If a repository is not listed in the .tsv file, no changes will be made if the same repository exists in the Git Integration app configuration.

