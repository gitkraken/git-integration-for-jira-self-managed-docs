---

title: Editing existing repository settings in the TSV File
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Navigate to the .tsv file and edit it with your favorite spreadsheet program.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <a href='http://drive.google.com/'><b>Google Drive</b></a> is also a recommended place to edit the .tsv file.
    </div>
    </div>
</div>

&nbsp;

Populate/edit the fields by utilizing the following options:

### id

_Integer_. Required.

Assign an ID number to a repository.

This field is required if you wish to update or edit existing repositories by setting this value to their equivalent IDs. Otherwise, if this field is left blank, the repository will be created as new.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Important!</b><br>
        When importing to a new server, the <b><i>id</i></b> field must be blank.
    </div>
    </div>
</div>

### realRoot

_String_. **Optional on existing servers**.

This is the local path to the repository on the server where your Jira service is running. This will point the Git Integration for Jira app to a clone of the repository hosted locally with Jira.

The `realRoot` field may refer to an existing repository on a new server. If `root` doesn't exist, this field must be blank.

### absoluteRoot

_Boolean_. Optional.

This field corresponds to the _**Cloned root location**_ input field in the Advanced setup/Repository settings.

If this field is set to `true`, the repository is automatically managed by Git Integration for Jira app (stored in `$JiraHOME`). If set to `false`, the repository is manually configured by the Jira administrator.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If this field is specified, <code>realRoot</code> must also be defined.
    </div>
    </div>
</div>

### origin

_String_. Required.

This is the URL to the hosted git service used on the project. For example, you might host your repository on GitHub, Beanstalk or your own server.

#### SSH INTEGRATION

Before adding repositories (new or existing) via Bulk change, make sure that you have added SSH keys for the respective git hosts in the Git Integration for Jira app configuration page. BigBrassBand recommends to use the `git@<url>:[your-git-repo].git` format for the repository origin URL and [adding of SSH Keys](/git-integration-for-jira-data-center/adding-a-private-ssh-key-gij-self-managed) for each git host in the Git Integration for Jira app configuration page.

#### HTTPS/HTTP INTEGRATION

For HTTPS git repositories, obtain the URL from your git host. If you use HTTP/HTTPS URLs in the origin field, the Git Integration for Jira app will not be able to import said repositories due to missing credentials. Entering repository login credentials in the TSV file is not advisable due to a possible security risk. Therefore, when editing the _**origin**_ field of the TSV file, enter value using the `git@<repository-url>:[your-git-repo].git` format. This format will use the SSH key(s) from the Git Integration for Jira app configuration instead.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The repository origin may not be hosted on the same server as Jira.
    </div>
    </div>
</div>

### displayName

_String_. Optional.

Define a meaningful name for this repository configuration. This is the name that will appear in the Git Integration for Jira app repositories list. If this field is left blank, the default value is obtained from the origin.

### enableFetches

_Boolean._ Optional.

Set to `true` to enable fetches on git repositories hosted on remote servers. In this mode, fetches are enabled using any external source. The reindex background service will initiate the fetch then add the new commits to the plugin index.

Set to `false` to enable fetches on git repositories hosted on the same server as Jira. Fetches are enabled when the repository is hosted locally. In this mode, no fetches are made. The reindex service runs in the background and process every new commit found.

### revisionIndexing

_Boolean_. Optional.

The default value for this field is `true`.

This option turns on the memory cache which is used when list of commits are displayed. Set to `true` if revision indexing will index and link to any mentioned issue keys in the revision history or not (`false`).

### mainBranch

_String._ Optional.

Set specific branch as the main branch for this repository. A commit will not be shown in other branches if it is a part of the main branch. By default, `master` will be used if a main branch is not specified.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Default Main Branch</b><br>
        Most git integrations allow changing of the default branch of the repository/project other than <code>master</code> at the server level. On each reindex, this change is reflected in the Repository Settings. In the case of Gerrit, the default main branch is always <code>master</code>.
    </div>
    </div>
</div>

### username, password

_String_. Optional.

Critical for https origins. Define `username` and `password` for the git host. Leave blank if 2FA is enabled in your git host.

### pat

_String_. Optional.

Required, if 2FA is enabled for the git host. This field accepts personal access token from supported git hosts.

### gitViewerEnabled

_Boolean._ Optional.

Enables or disables the **Repository Browser** feature for this repository. The default setting for this field is `enabled`.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Users must have the <b>View Development Tools</b> <i>project permission</i> in order to use this feature. Consult your Jira System Administrator on permissions.
    </div>
    </div>
</div>

For more information, see [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed).

### projectMapping

_Long \[ \]_. Array. Optional.

These are numeric projects IDs associated with the repository.

*   This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored _(equivalent to unchecking the **Associate to All Projects** checkbox)_.

    _Example:_ `10000,10100`

*   If you change an existing repository, leaving this field blank will use the existing values of the repository configuration.

*   Setting this field to `ALL` will retain _**projectMapping**_ settings and sets the "All Projects" flag to `true` _(equivalent to checking the_ **Associate to All Projects** _checkbox)_.

*   If projects are not associated to the repository, you must leave this field blank and set the _**gitViewerEnabled**_ field to `false`.

### smartCommitsEnabled

_Boolean._ Optional.

Enables/disables smart commits processing for this repository or tracked folder. The default value for this field is `true`.

### sendCommitEmails

_Boolean._ Optional.

Enables or disables commit notification emails for this repository. If left blank, the default value for this field is `true`.

### maxMinsToCommitEmail

_Integer_. Optional.

Set the desired value in minutes, as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value.

### changesetFormat, fileAddedFormat, fileModifiedFormat, fileDeletedFormat

_String._ Optional.

This is the URL to display content of added, modified or deleted files. Use the following variables:

<ul>
    <li>`${num}` –  number of change (0, 1, …)</li>
    <li>`${rev}`  –  git revision</li>
    <li>
        `${path}` –  path of the file being changed</li><li>`${sha256path}`  –  sha256 applied to the path and hex encoded. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> in v4.17+ and is used in <b>GitHub.com</b> weblinking.
    </li>
    <li>
        `${md5}`  –  md5 applied to the path and hex encoded. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> in v4.17+ and is used in <b>GitHub EE</b> weblinking.
    </li>
    <li>
        `${sha1path}`  –  sha1 applied to the path and hex encoded. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> in v4.17+ and is used in <b>GitLab</b> weblinking.
    </li>
    <li>`${parent}` –  parent git revision</li>
    <li>`${blob}`  –  ID of blob object</li>
    <li>`${parent_blob}` – ID of parent blob object</li>
    <li>
        `$convert(${branch},"subStr","newSubStr")` – this inline function returns branch name with `subStr` replaced by a `newSubStr`.
    </li>
</ul>

<div class="bbb-callout bbb--info" style='margin-bottom:0px;'>
    <div class="irow">
        <div class="ilogobox"><span class="logoimg"></span></div>
        <div class="imsgbox">
            The <code>${branch}</code> code has been changed to cope up with the character requirements on some hosting services.
        </div>
    </div>
</div>

### disabled

_Boolean_. Optional.

Add this repository into the Git Integration app configuration and set its status to updated (_enabled_) or disabled. If left blank, the default value for this field is `false`.

### hosted

_Boolean._ Optional.

**Internal field**. Read-only. This field will show whether the repository is hosted on Jira or not.

### tagsFilter

_String._ Optional.

Displays all tags for the specific issue, if left blank. Otherwise, set tags matching pattern to display tags on issue pages that match the specified regular expression pattern.

Set _**tagsFilter**_ with a valid Java regular expression or an empty string. The filtered tags are displayed on the Jira Developer Panel.

For more information, see example in [Git tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed).

### requireUserPat

_Boolean_. Optional.

Setting this field to `true` will require users to specify their own PAT for branch and pull/merge request management. If left blank, the default value of this field is `false`.

### integrationType

_Boolean._ **Internal field**.

This field will show whether the repository is a tracked folder, a connected GitLab server or a simple repository.

### trackedFolderId

_Integer._ **Internal field**.

This field will display the ID of the "parent" repository. It can be changed in order to convert the repository to a sub-repository.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Use with caution</b><br>
        If the modified sub-repository is not located in the tracked folder, it will be removed by the sequential auto-reindex.
    </div>
    </div>
</div>

### delete

_Flag_. Optional.

Set **"delete"** on this column/field as a confirmation to the Git Integration app to automatically remove the selected repository from the plugin configuration. If left blank, no changes will occur.

### sshKeyId

_Integer_. Optional.

This is the ID of an associated SSH key.

### sourcesDiffViewEnabled

_Boolean._ Optional.

When enabled, this setting allows Jira users with the **View Development Tools** and correct Jira/Git Integration for Jira app permissions to view the commit and file diffs inside Jira.

### apiPath

_String_. Optional.

The integration will use this relative REST API path starting with "/" to retrieve the list of tracked repositories.

For more information, see [Working with Custom API Path](/git-integration-for-jira-data-center/working-wit-custom-api-path-gij-self-managed).

### apiFilter

_String_. Optional.

JMESPath filter expression will be used to filter API results.

See our [Integration Guides](/git-integration-for-jira-data-center/integration-guides-gij-self-managed), [Working with JMESPath filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed) or [contact support](mailto:gijupport@gitkraken.com) for help writing expressions.

### tfsCollection

_String_. Optional. TFS or Azure DevOps Server integrations only.

A TFS collection is a group of TFS team projects. Specify an existing TFS Collection for use with Jira integration.

### awsRegion

_String_. Optional. AWS integrations only.

Specify AWS region; where CodeCommit repositories are located. The list of regions with their names can be found <a href='https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html' target='_blank'><b>here</b></a>.

Git Integration for Jira app supported regions:

| Region codes |  |  |  |
|:--|:--|:--|:--|
| us-east-1 | us-east-2 | us-west-1 | us-west-2 |
| ap-south-1 | ap-northeast-2 | ap-southeast-1 | ap-southeast-2 |
| ap-northeast-1 | ca-central-1 | eu-central-1 | eu-west-1 |
| eu-west-2 | eu-west-3 | eu-north-1 | me-south-1 |
| sa-east-1 | | | |

### sslVerify

_Boolean_. Optional.

Default is `TRUE`. The **SSL Verify** option is set to enabled by default. If set to `FALSE`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting can also be accessed via menu Git ➜ Manage repositories ➜ <img src='/wp-content/uploads/actions-icon.png' /> <i>Actions</i> ➜ <b>Edit repository/integration settings</b>.
    </div>
    </div>
</div>

### trustFolderStat

When this field is set to `false`, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to `true`, the `last-modified` attribute of the folder will be used to check the folder for modifications.

The default value for Jira Server is `true`.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The default value for Jira Data Center is <b>false</b>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If your repository is stored on a network share, it is highly recommended to set this field to <b>false</b>.
    </div>
    </div>
</div>

### weblinkType

_String._ Optional.

Set web link type equivalent to the connected git host. Set web linking formats by referring to [Documentation – Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed).

### viewFormat

_String._ Optional.

This is the URL to display diff from some git hosts. Other git hosts does not use this field.

### mergeRequestFormat

_String._ Optional.

This is the URL to display content of pull/merge requests on the git server.  Use the following variables:

`${mergereqId}` – ID of the pull/merge request

### branchLinkFormat

_String._ Optional.

This is the URL to display a branch on the git server. Use the following variables:

`${branch}` – Name of the branch

### refSpecNotes

_Boolean_. Optional.

This is a reference to `refs/notes/*` used for fetching. The default value for this field is `false`.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Git notes are not shown...
        <ul>
            <li>when `refs/notes` are disabled on connecting a repository;</li>
            <li>when a new note comes when `refs/notes` is disabled.</li>
        </ul>
    </div>
    </div>
</div>

### refSpecChanges

_Boolean_. Optional.

This is a reference to `refs/changes/*` used for fetching. The default value for this field is `false`.

### refSpecCustom

_String_. Optional.

This is a user-defined list of references used for fetching. It is a comma-separated list with the format:

`+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

## prHideFilter

_String_. Optional.

Displays all pull requests for the specific issue, if left blank. Otherwise, set pull requests matching pattern to hide pull requests on issue pages that match the specified regular expression pattern.

&nbsp;
* * *

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Take note that the .tsv file is verified by the Git for Jira app with the following rules:
        <ul style='margin-bottom:0px !important;'>
            <li>The header row is required.</li>
            <li>The order of fields specified in the header row – is the order of the fields in the following rows.</li>
            <li>If a field is omitted from the header row, the Git Integration app will use the default value for a new repository. The Git Integration app will keep the current value of a repository if it already exists in the configured repositories.</li>
            <li>If a repository is not listed in the .tsv file, no changes will be made if the same repository exists in the add-on configuration.</li>
        </ul>
    </div>
    </div>
</div>
<br>

Save the file to a tab-delimited format:

*   **OSX users** – select all data in Numbers and then paste into a text editor and save. Name the file with the **.tsv** extension (_repo-example-00.tsv_).

*   **Excel users** – save the file as **Text (Tab delimited) (\*.txt)**. Rename file's **.txt** extension to **.tsv**.

*   **Google Drive** - upload the file to this service. Right click the **.tsv** file then open it with _Google Sheets_.  Make the necessary changes then go to File ➜ Download as ➜ **Tab separated values (.tsv)** to your local machine.

&nbsp;
<hr>
&nbsp;

[**Prev:** Import new repositories via Bulk change](/git-integration-for-jira-data-center/import-new-repositories-via-bulk-change-gij-self-managed)

[**Next:** Removing existing repositories via Bulk change](/git-integration-for-jira-data-center/removing-existing-repositories-via-bulk-change-gij-self-managed)

&nbsp;

## More related articles on Bulk change

[Exporting repository configuration via Bulk change](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed)

[Requirement for secured import](/git-integration-for-jira-data-center/requirement-for-secured-import-gij-self-managed)

[Import existing repositories via Bulk change](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed)

[Import new repositories via Bulk change](/git-integration-for-jira-data-center/import-new-repositories-via-bulk-change-gij-self-managed)

**Editing existing repository settings in the TSV File** (this page)

[Removing existing repositories via Bulk change](/git-integration-for-jira-data-center/removing-existing-repositories-via-bulk-change-gij-self-managed)

[Bulk change (index)](/git-integration-for-jira-data-center/bulk-change-gij-self-managed)

