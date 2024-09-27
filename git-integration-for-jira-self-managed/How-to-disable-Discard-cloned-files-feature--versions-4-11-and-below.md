---

title: How to disable "Discard cloned files" feature (Windows/Linux)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Remove Discard files feature is deprecated and the purpose of this article is to guide you on how to completely disable this setting while preserving all integration settings such as project mapping, users' PATS and other integration settings.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This guide applies to Jira instance with GIJ v4.11 and below.
    </div>
    </div>
</div>

&nbsp;

### 1\. Update Git Integration for Jira

Upgrade to the latest version of [Git Integration for Jira](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?tab=overview&hosting=datacenter) supporting the _**Discard cloned files**_ feature (GIJ v4.16 as of now).

Go to the **Manage apps** page and expand Git Integration for Jira under Installed apps.

![GIJ under Installed apps showing Update button highlighted](/wp-content/uploads/gij-docs-installation-plugin-update-c.png)

Click **Update** to upgrade the Git Integration for Jira app to the newest version.

&nbsp;

### 2\. Verify that a Git client is installed

Make sure that a Git client is installed on the machine where the Jira instance is running.. Use the following command to check the installed Git version:

```bash
git --version
```

&nbsp;

### 3\. On Windows, verify installed Powershell version (skip this step for Linux)

Ensure that PowerShell version 5.x or higher is installed on the machine where the Jira instance is running.

![Shows the PowerShell version command example in the Command prompt window](/wp-content/uploads/gij-check-powershell-version.png)

&nbsp;

### 4\. Disable webhooks on "Webhooks" page

On the Manage repositories page, click **Webhooks** on the sidebar then click **Disabled**.

![Shows how to access the Webhooks page via Git menu then Manage repositories then on the sidebar click on Webhooks tab then click on Disabled radio button](/wp-content/uploads/gij-gitserver-gitmgr-manage-webhooks.png)

&nbsp;

### 5. Take note of the following General settings

Make sure to write down the following settings and save it for use later:

*   **Repository indexing interval**

*   **Garbage collection and Revision validation interval**

*   **Git roll up issue tab**

*   **Git commits issue and project tabs**

Then, set the scheduled job frequency to a large value. For example:

*   Repository indexing interval = **100000**

*   Garbage collection and Revision validation interval = **100000**

Also, disable the following settings to make GIJ repositories temporarily unavailable:

*   Set Git roll up issue tab to Do not display

*   Set Git commits issue and project tabs to Do not display

*   Untick the Enable repository browser setting

*   Untick the Show Git Integration panel on issue pages setting

*   Untick the Enable Automation for Jira (A4J) triggers setting

*   Untick the Enable JQL searching using commit information setting

&nbsp;

### 6\. Disable all repositories/integrations via Actions

Click the **Disable all** button on the Manage repositories page.

![Shows Manage repositories page while highlighting the "Disable all" button](/wp-content/uploads/gij-gitserverdc-gitmgr-disable-all-sel.png)

&nbsp;

### 7\. Clear the indexing queue

On your Jira dashboard Git menu, click **Indexing queue**.

Click on the **Clear queue** button to clear the indexing queue.

<img src='/wp-content/uploads/gij-gitserver-indexing-queue-viewer-dashboard.png' alt='Shows the Indexing queue viewer dashboard panel with the Clear queue button' style='margin:25px auto;max-width:100%;display:block;' />

&nbsp;

### 8a\. Powershell script for Windows

```powershell
#requires -version 5
[CmdletBinding()]
param (
    [Parameter(Mandatory=$false,Position=0)]
    [string]$FullRun
)

$ErrorActionPreference = 'Stop'

$ScriptDirectory = Split-Path -Path $PSScriptRoot -Leaf
if ( $ScriptDirectory -ne "git-plugin" ) {
    Write-Output "The script should be run in jira/home/data/git-plugin directory! Current directory is `"$PSScriptRoot`"."
    return
}

function Remove-Tree()
{
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        [string]$Path
    )

    if ( Test-Path -LiteralPath $Path -PathType Container ) {
        @(Get-ChildItem -LiteralPath $Path -Directory -Force).ForEach({ Remove-Tree -Path $_.FullName })
        @(Get-ChildItem -LiteralPath $Path -File -Force).ForEach({ Remove-Item -LiteralPath $_.FullName -Force })
    }
    Remove-Item -LiteralPath $Path -Force
}

function Clear-GitRepo()
{
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        [string]$GitRepoFolder
    )

    Set-Location -LiteralPath $GitRepoFolder
    Write-Output ""

    if ( -not (Test-Path -LiteralPath 'config' -PathType Any) ) {
        Write-Output "skip $GitRepoFolder folder. It doesn't contain config."
        Set-Location -Path ".."
        return
    }

    Write-Output "delete files from $GitRepoFolder except 4 files: config, HEAD, repo.auto.json, repo.auto.json.gitforjira.lock"

    @(Get-ChildItem -Force | Where-Object {$_.Name -notin "config", "HEAD", "repo.auto.json", "repo.auto.json.gitforjira.lock"}).ForEach({
        Remove-Tree -Path $_.FullName
    })

    $isHeadExists = Test-Path -LiteralPath 'HEAD' -PathType Any
    if ( $isHeadExists ) {
        Write-Output "move 'HEAD' to 'HEAD-gij-backup' file"
        Move-Item -Path 'HEAD' -Destination 'HEAD-gij-backup' -Force
    }

    Write-Output "init a bare repository with the same config"
    $DummyDir = 'non-existent-git-template-directory'
    try {
        git init --bare --template=$DummyDir --quiet
    }
    catch [System.Management.Automation.RemoteException] {
        if ( -not ($_.Exception -like "*$DummyDir*") ) {
            throw
        }
    }

    if ( $isHeadExists ) {
        Write-Output "restore 'HEAD' file"
        Move-Item -Path 'HEAD-gij-backup' -Destination 'HEAD' -Force
    }

    Set-Location -Path ".."
}

function Test-RunType()
{
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        [string]$GitRepoFolder,

        [Parameter(Mandatory=$true)]
        [boolean]$IsFullRun
    )

    if( $IsFullRun ) {
        Clear-GitRepo -GitRepoFolder $GitRepoFolder
    } else {
        Write-Output (Split-Path -Path $GitRepoFolder -Leaf)
    }
}

git --version
Write-Output ""

$IsFullRunSet = $PSBoundParameters.Count -ge 1
if ( $IsFullRunSet ) {
    Write-Output "Processing of Git repositories has been started. It may take several minutes so please be patient."
}
@(Get-ChildItem -Path "." -Directory -Force -Exclude "scripts","weblinking").ForEach({
    Test-RunType -GitRepoFolder $_ -IsFullRun $IsFullRunSet
})
```

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Save this script to <b>clearDataInRepositories.ps1</b>.
    </div>
    </div>
</div>

&nbsp;

### 8b\. ShellScript for Linux

```shell
#!/bin/bash
set -eo pipefail

clearGitRepo(){
    cd "${1}"
    echo ""

    if [[ ! -f "config" ]]; then
        echo "skip ${1} folder. It doesn't contain config."
        cd ..
        return 0
    fi

    echo "delete files from ${1} except 4 files: config, HEAD, repo.auto.json, repo.auto.json.gitforjira.lock"

    find . -maxdepth 1 ! -name 'config' ! -name 'HEAD' ! -name 'repo.auto.json' ! -name 'repo.auto.json.gitforjira.lock' ! -name '.' ! -name '..' -exec rm --force --recursive {} \;

    IS_HEAD_EXISTS=true
    if [[ ! -f "HEAD" ]]; then
        IS_HEAD_EXISTS=false
    fi

    if $IS_HEAD_EXISTS; then
        echo "move 'HEAD' to 'HEAD-gij-backup' file"
        mv --force HEAD HEAD-gij-backup
    fi

    dummyDir=non-existent-git-template-directory
    echo "init a bare repository with the same config. Ignore the next warning if it says about '${dummyDir}'."
    git init --bare --template=${dummyDir} --quiet

    if $IS_HEAD_EXISTS; then
        echo "restore 'HEAD' file"
        mv --force HEAD-gij-backup HEAD
    fi

    cd ..
}
export -f clearGitRepo

dryOrNot(){
    if [ -z "${1}" ]; then
        cat <&0
    else
        xargs --max-args=1 --delimiter='\n' bash -c 'clearGitRepo "${0}"'
    fi
}
export -f dryOrNot

SCRIPT_DIRECTORY=$(basename $PWD)
if [ "${SCRIPT_DIRECTORY}" != "git-plugin" ]; then
    echo "The script should be run in jira/home/data/git-plugin directory! Current directory is '$SCRIPT_DIRECTORY'."
    exit 1
fi

git --version
echo ""

ls --directory */ | grep --invert-match --word-regexp --extended-regexp 'scripts/|weblinking/' | dryOrNot "${1}"
```

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Save this script to <b>clearDataInRepositories.sh</b>.
    </div>
    </div>
</div>

&nbsp;

### 9\. Review repository folders that will be cleared

Run the script without arguments in `jira/home/data/git-plugin` folder to preview which repository folders are going to be cleared.

On Windows (in PowerShell console):
`.\clearDataInRepositories.ps1`

On Linux (Terminal):
`./clearDataInRepositories.sh`

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Important!</b><br>
        For mounted shared folders on the same server as Jira, you will need to unmount them first before proceeding to <b>step 10</b>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        If your Jira self-managed instance and Git repositories are on the same server – the git repositories are not affected since the script execution in step 10 will only process the folder where the cloned repositories reside (<code>jira/home/data/git-plugin</code>). It is dangerous if any of the folders is not a clone created by the GIJ plugin (i.e. <i>if it’s the origin Git repository and it does not have other full clones</i>).
    </div>
    </div>
</div>

&nbsp;

### 10\. Clear the repository clone folders

The script loops through all the folders in `jira/home/data/git-plugin` (where the cloned repositories reside). For each folder, the contents are deleted such as git files structure (except several **config** files) and initializes a bare Git repository using the same configuration.

Execute the script with one argument in jira/home/data/git-plugin folder on behalf of the Jira user ([read here](/git-integration-for-jira-data-center/faq-general-gij-self-managed/#how-to-obtain-the-correct-jira-user-name)):

On Windows (in PowerShell console):
`.\clearDataInRepositories.ps1 go`

On Linux (Terminal):
`./clearDataInRepositories.sh go`

&nbsp;

### 11\. Disable the Remove Discard files setting

1.  Go to **General settings** (_Jira dashboard menu Git ➜ Manage repositories ➜ General settings [left sidebar]_).

    ![Shows how to access the General settings page -- Git menu then Manage repositories then click General settings on the sidebar](/wp-content/uploads/gij-gitserverdc-general-settings-acc.png)

2.  Scroll down to the **Advanced settings** and click to expand the hidden options.

    ![Shows the General settings page where Advanced settings is highlighted](/wp-content/uploads/gij-gitserverdc-general-settings-advanced-sel.png)

3.  For the _**Discard cloned files in Jira home directory**_ setting, set it to **Keep all cloned files. No storage savings. All features available**.

&nbsp;

### 12\. Enable all the repositories/integrations back

On the Manage repositories page, click the **Enable all** to reconnect all integration repositories to Git Integration for Jira.

![Shows the Manage repositories page highlighting the Enable all button](/wp-content/uploads/gij-gitserverdc-gitmgr-enable-all-sel.png)

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you only plan to enable specific repositories, use the checkboxes at the Enabled column of the repositories list.
    </div>
    </div>
</div>

&nbsp;

### 13\. Perform a Reset all of the indexes

On the Manage repositories page, click on Indexing ➜ **Reset all indexes**.

![Shows where to access this function -- Manage repositories page then click on Indexing drop down then click "Reset all indexes"](/wp-content/uploads/gij-gitserver-reindex-reset-index-all.png)

&nbsp;

### 14\. Revert back the Generals settings

Change back the following settings to the saved values from step 5:

*   **Repository indexing interval**

*   **Garbage collection and Revision validation interval**

*   **Git roll up issue tab**

*   **Set Git commits issue and project tabs**

Also, enable the following settings to make GIJ repositories available again:

*   Tick on the **Enable repository browser** setting

*   Tick on the **Show Git Integration panel on issue pages** setting

*   Tick on the **Enable Automation for Jira (A4J) triggers** setting

*   Tick on the **Enable JQL searching using commit information** setting

&nbsp;

### 15\. Enable back webhooks

On the Manage repositories page, click **Webhooks** on the sidebar then click **Enabled**.

&nbsp;
* * *
&nbsp;

## Related admin articles

[Tips for Jira Administrators](/git-integration-for-jira-data-center/tips-for-jira-admins-gij-self-managed/) (Git Integration for Jira Data Center)

[Migrating from Jira 8 to Jira 9](/git-integration-for-jira-data-center/migrating-jira7-to-jira9-gij-self-managed/) (Git Integration for Jira Data Center)

[Upgrades and migrations within same server](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed/) (Git Integration for Jira Data Center)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed/) (Git Integration for Jira Data Center)

[General Settings](/git-integration-for-jira-self-managed/general-settings-gij-self-managed) (Git Integration for Jira Data Center)

[Recommended Jira memory settings](/git-integration-for-jira-self-managed/recommended-jira-memory-settings-gij-self-managed) (Git Integration for Jira Data Center)

[Scheduling Jobs](git-integration-for-jira-self-managed/scheduling-jobs-gij-self-managed) (Git Integration for Jira Data Center)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed/) (Git Integration for Jira Data Center)

[Administration FAQ](/git-integration-for-jira-self-managed/Faq-administration-gij-self-managed) (Git Integration for Jira Data Center)

[Indexing queue explainer](/git-integration-for-jira-self-managed/indexing-queue-explainer-gij-self-managed) (Git Integration for Jira Data Center)

&nbsp;

## See other how-to articles

*   [How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed)

*   [Setting Project Permissions](/git-integration-for-jira-data-center/setting-project-permissions-gij-self-managed)

*   [How to create a HAR file and send it to support for analysis](/git-integration-for-jira-data-center/how-to-create-a-har-file-and-send-it-to-support-for-analysis-gij-self-managed/)

*   [How to disable "Discard cloned files" feature (Windows/Linux)](/git-integration-for-jira-data-center/How-to-disable-Discard-cloned-files-feature--versions-4-11-and-below)

*   [Working with Custom API Path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed)

*   [Working with JMESPath Filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed)

*   [Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

*   [Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

*   [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed)

*   [Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/ways-to-index-git-data-to-jira-issues-gij-self-managed)

*   [Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/proxy-settings-on-adding-integrations-except-aws-codecommit-gij-self-managed)

*   [Creating Personal Access Tokens](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed)

