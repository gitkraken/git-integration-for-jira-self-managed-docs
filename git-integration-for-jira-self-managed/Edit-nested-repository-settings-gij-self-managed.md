---

title: Edit nested repository settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## How to edit a nested repository with Git Integration for Jira app?

### Pre-GIJ version 5.x.x

Go to the Manage integrations configuration page and choose an integration with the nested repository to manage.

1.  Click &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Action ➜ **Show integration repositories**.

    ![](/wp-content/uploads/gij-datacenter-pre-5x-actions-show-repos.png)

2.  Navigate or look for the nested repository that you want to edit. When found, click the repository name to take you to it’s git configuration page.

    ![](/wp-content/uploads/gij-datacenter-pre-5x-show-integration-repos.png)

3.  With screens similar to the Edit repository settings page (see next section), make some necessary changes to the selected nested repository and then click Save to save your changes.

### GIJ version 5.x

Go to the Manage repositories configuration page and navigate to the nested repository you want to manage.

1.  For that nested repository, Click <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit repository**.

    ![](/wp-content/uploads/gij-datacenter-5x-manage-repos-nested.png)

2.  On the **Settings for Repository** page, make the necessary changes as desired (see next section). Click **Save** to save the changes.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For Azure DevOps Server and GitHub Enterprise, by default, only PAT is available for editing. Regardless of whether the integration was previously installed with user/password or not.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        When adding a nested repository to an integration - no SSH key is inherited from the integration because it does not carry the SSH key.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The login credentials are not inherited with nested repositories to interact with external APIs and .git is based on the integration's credentials.
    </div>
    </div>
</div>

&nbsp;

## Edit nested repository settings

Utilize the options below for configuring repository settings:

| Option | Description | Type |
| :--- | :--- | :--- |
| _**Display Name**_ | This is the alias that will appear in the Repository/Integration column. | HOSTED<br>EXTERNAL |

&nbsp;

### Cloned repository root

| Option | Description | Type |
| :--- | :--- | :--- |
| _**Absolute Repository Root**_ | This is the calculated absolute path of the clone repository root on the same machine as Jira. | HOSTED<br>EXTERNAL |
| _**Clone root location**_ | Set to automatically managed or manually configured by Jira admin. | EXTERNAL |
| _**Repository Root**_ | This is the path to a clone of the repository. | EXTERNAL |

&nbsp;

### Repository Settings

| Option | Description | Type |
| :--- | :--- | :--- |
| _**Enable Fetches**_ | Set to either hosted at remote server or hosted on the same server as Jira. | EXTERNAL |
| _**Repository origin**_ | Full URL to the Git origin from where the repository was cloned. | HOSTED<br>EXTERNAL |
| _**Main Branch**_ | Set the main branch. Default is `master`. | HOSTED<br>EXTERNAL |
| _**Use HTTP(S) Authentication**_ | If this repository connection supports HTTP(S) authentication, turn on this feature and enter the required username and password credentials here. | EXTERNAL |
| _**SSL Verify**_ | If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a remote Git server. | EXTERNAL |
| _**TrustFolderStat**_ | When this setting is set to `False`, the objects/pack folder will always be scanned to check for new pack files. If set to `True`, the `last-modified` attribute of the folder will be used instead to check the folder for modifications.<br><div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"> <span class="logoimg"></span></div><div class="imsgbox">The default value for Jira Server is <code>True</code>. For Jira Data Center, it's <code>False</code>.</div></div></div> <div class="bbb-callout bbb--note"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your repository is stored on a network share, it is highly recommended to set this option to <code>False</code>.</div></div></div> | HOSTED<br>EXTERNAL |

### Other settings
| Option | Description | Type |
| :--- | :--- | :--- |
| _**Repository Browser**_ | When `Enabled`, it allows users to view Git repositories of configured projects. For more information, see [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed). | HOSTED<br>EXTERNAL |
| _**Tags**_ | Set whether to show all tags or show on tags with matching regex pattern. For more information on git tags, see [Git tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed). | HOSTED<br>EXTERNAL |
| _**Pull requests**_ | Set whether to show all pull requests or show on pull requests with matching regex pattern. | HOSTED |
| _**Project Permissions: Restrict to projects**_ | The default setting is **Associate with all projects**. You can restrict access to the Repository Browser and Git Commit tabs (Advanced) for the selected repository by setting the project associations. | HOSTED<br>EXTERNAL |
| _**Source Code Diff Viewing**_ | Allows or disallows users to view the diff by commit and file. | HOSTED<br>EXTERNAL |
| _**Smart Commits**_ | Allows or disallows users to use the smart commits feature. | HOSTED<br>EXTERNAL |
| _**Commit Notification Emails**_ | Allow or disallow sending of commit notification emails.<br><br>Set the **Max commit age (in minutes)** as desired. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. | HOSTED<br>EXTERNAL |
| _**Web Linking**_ | _Optional._<br><br>The web linking feature adds links to your git hosting provider directly into the Git Commits tab. For special integrations (Auto-Connect), this feature is configured automatically. For more information on about this topic, see [Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed). | HOSTED<br>EXTERNAL |

&nbsp;
* * *

[**Prev:** Adding a nested repository](/git-integration-for-jira-data-center/adding-a-nested-repository-gij-self-managed)

[**Next:** SSL verify](/git-integration-for-jira-data-center/edit-nested-repository-settings-gij-self-managed)


