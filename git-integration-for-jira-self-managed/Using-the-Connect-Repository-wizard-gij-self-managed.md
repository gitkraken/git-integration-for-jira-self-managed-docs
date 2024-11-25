---

title: Using the Connect Repository wizard
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

This page is intended for users who are using SSH connections or those who wanted to only connect a single specific repository.

**What’s on this page:**
- [Getting started](#getting-started)
- [Settings](#settings)
- [HTTP(S) authentication](#https-authentication)
- [SSH authentication](#ssh-authentication)
- [Passphrase Input](#passphrase-input)
- [More related topics on setting up repositories](#more-related-topics-on-setting-up-repositories)

&nbsp;
* * *
&nbsp;

### Getting started

Navigate to the Manage repositories page.

![](/wp-content/uploads/gij-gitserver-gitmgr-connect2git-sel.png)

<div align='center' style='margin-top:10px;margin-bottom:30px;'>
    <i><b>Figure 1:</b> Connect wizard start screen.</i>
</div>

To start integrating a plain git repository, follow the steps below:

1.  Click **Connect to Git Repository**. The connect repository wizard is displayed:

    ![](/wp-content/uploads/gij-gitserver-connect-git-wizard-start-screen.png)

2.  Enter required repository location. The **Repository location** can be any type of supported gitl URL protocols as stated in the _**Location type**_ examples.

3.  Click **Next**. The Connect wizard will automatically detect the provided repository location type.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Detection of Remote Origin Setting</b><br>
        The detection works for most repositories. If a repository root points to a valid git repository, the repository origin is detected automatically. When a repository has no origin, the user has to specify it manually.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Do note that the Connect wizard <b>clones the remote repository by default</b>. It does not clone local repositories. For local repositories, the `root` is set to local path and fetches are disabled.
        <p style='margin-bottom:0px !important;'>
            The default identities are not used and the repository is created without the additional key upload.
        </p>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the Git repository file system is somehow available to the Jira server, you can save the clone step and save the disk space on a Jira server by pointing the Jira server straight at it.
    </div>
    </div>
</div>

&nbsp;

### Settings

In the **Settings** screen, you can configure features such as [Smart Commits](/git-integration-for-jira-data-center/smart-commits-gij-self-managed), [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed) and [Project Permission](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed) settings.

![](/wp-content/uploads/gij-connect-git-wizard-cfg-screen.png)

<div align='center' style='margin-top:10px;margin-bottom:30px;'>
    <i><b>Figure 2:</b> Settings screen at the end of the Connect wizard.</i>
</div>
<br>

*   **Smart Commits**  – Enable or disable this setting to allow processing of smart commits for this repository connection.

*   **Repository Browser** – Enable or disable this setting to allows users to view git repositories of configured projects via the **Git** menu on the Jira dashboard. This feature is only available on Jira Server/DC instances.

*   For _**Project Permissions**_, set one or more projects in the **Restrict to projects** field to map this repository and make the **Git Commits** tab available in the **Issue** pages of the associated projects. Otherwise, leave the _**Associate with all projects**_ state to <img src='/wp-content/uploads/gij-matrix-open-check-green.png' width=20 height=20 style='margin:0 3px' /> associate this repository to all projects.

The level of permissions can be one of the following:

<table>
    <thead>
        <tr>
            <th width=150><b>Level</b></th>
            <th><b>Process</b></th>
        </tr>
    </thead>
    <tbody>
        <tr valign='baseline'>
            <td><b>Repository</b></td>
            <td>
                <div>Select a repository from the repository list. For repositories inside integrations, view the integration then select a repository within <i>(<img  src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Show integration repositories)</i>. After the selection, you will be taken to the repository properties.</div>
                <p>Set the <b>Project Permissions</b> as follows:</p>
                <ol style='margin-bottom:0 !important'>
                    <li>Uncheck the <b>Associate with all projects</b> option.</li>
                    <li>Click the <b><i>Restrict to project</i></b> field and select one or more project(s).</li>
                    <li>Save/Update the repository settings.</li>
                </ol>
            </td>
        </tr>
        <tr>
            <td valign='baseline'><b>Integration</b></td>
            <td>
                <div>
                    Select an integration from the repository list then open the integration feature properties <i>(<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Edit integration feature settings)</i>.
                </div>
                <p>Set the <b>Project Permissions</b> as follows:</p>
                <ol style='margin-bottom:0 !important'>
                    <li>Uncheck the <b>Associate with all projects</b> option.</li>
                    <li>Click the <b><i>Restrict to project</i><b/> field and select a project.</li>
                    <li>Save/Update the repository settings.</li>
                </ol>
            </td>
        </tr>
        <tr>
            <td><b>All</b></td>
            <td>
                This is the default setting where the <b>Associate to all projects</b> option is in state.
            </td>
        </tr>
    </tbody>
</table>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For Project Permissions, the <b>View Development Tools</b> <i>project permission</i> must be granted to Users ➜ Group ➜ <b><i>Project Roles</i></b>.
    </div>
    </div>
</div>

Click **Next**.

&nbsp;

### HTTP(S) authentication

If the entered git clone URL requires HTTP credentials, the following screen appears:

<img src='/wp-content/uploads/gij-connect-git-wizard-auth-scr-http-n.png' style='display:block;margin:25px auto;max-width:100%' />

<div align='center' style='margin-top:10px;'>
    <i><b>Figure 3:</b> HTTP authentication screen in the Connect wizard.</i>
</div>
<br>

Provide _**Username**_ and _**Password**_ in the respective fields then click **Next** to continue.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The HTTP authorization errors indicate that the credentials provided are not valid.
    </div>
    </div>
</div>

The HTTP authorization errors indicate that the credentials provided are not valid.

&nbsp;

### SSH authentication

For SSH git repository connections, the following screen is displayed for authentication:

<img src='/wp-content/uploads/gij-gitserver-ssh-connect-auth-screen.png' style='display:block;margin:25px auto;max-width:100%' />

<div align='center' style='margin-top:10px'>
    <i><b>Figure 4:</b> SSH authentication screen in the Connect wizard.</i>
</div>

Upload the private key file by clicking **Choose File** and navigate to the private key file. Otherwise, paste the private key text into the provided box.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For establishing safety connection with SSH, upload a public Key to the SSH server and set the private Key to the SSH client.
        <p style='margin-bottom:0 !important'>
            Take note that the SSH server is the Git server and the SSH client is the Jira server.
        </p>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        When adding a new repository that requires an SSH key, you can now pick an existing associated key in the <b><i>Existing key</i></b> list (see Figure 4).
    </div>
    </div>
</div>

Click **Next** to proceed.

&nbsp;

### Passphrase Input

If the generated SSH key pair has a passphrase, you will see the following screen:

<img src='/wp-content/uploads/gij-connect-git-wizard-auth-scr-pass.png' width=442 height=254 style='display:block;margin:25px auto 10px auto;max-width:100%' />

<div align='center' style="display:block;">
    <i><b>Figure 4:</b> SSH authentication screen in the Connect wizard.</i>
</div>

&nbsp;

Enter the _**Passphrase**_ for your private key. Click **Next** to continue.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The passphrase screen only appears if the user has added an SSH key that requires a passphrase.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app will initially try to use the keys provided by the user before using the keys from the home directory.
    </div>
    </div>
</div>

After the above requirements are fulfilled, the wizard will:

*   create a local copy of the git repository; and

*   index the git repository to build change history.

Click **Finish** to close the wizard.

This completes the setup and the newly added repository appears on the integration list on the Git Integration app repository configuration page.

&nbsp;
* * *

[**Prev:** Using the Add new integration wizard](/git-integration-for-jira-data-center/using-the-add-new-integration-wizard-gij-self-managed)

[**Next:** Connecting a repository via Advanced setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed)

&nbsp;

### More related topics on setting up repositories

[Git integration configuration page](/git-integration-for-jira-data-center/git-integration-configuration-page-gij-self-managed)

[Using the Add new integration wizard](/git-integration-for-jira-data-center/using-the-add-new-integration-wizard-gij-self-managed)

**Using the Connect Repository wizard** (this page)

[Connecting a repository via Advanced setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed)

[Adding a repository hosted on Windows Server or Windows Network Share](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-server-or-windows-network-share-gij-self-managed)

[Setup repository root not located in Jira HOME directory](/git-integration-for-jira-data-center/setup-repository-root-not-located-in-jira-home-directory-gij-self-managed)

[Tracked folders overview](/git-integration-for-jira-data-center/tracked-folders-overview-gij-self-managed)

[Self-signed HTTPS integration](/git-integration-for-jira-data-center/self-signed-https-integration-gij-self-managed)

[Managing repository or integration configuration](/git-integration-for-jira-data-center/managing-repository-or-integration-configuration-gij-self-managed)

[Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed)



