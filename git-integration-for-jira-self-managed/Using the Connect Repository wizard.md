---

title: Using the Connect Repository wizard
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
**What’s on this page:**
- [Getting started](#getting-started)
- [Settings](#settings)
- [HTTP(S) authentication](#https-authentication)
- [SSH authentication](#ssh-authentication)
- [Passphrase Input](#passphrase-input)


* * *

## Getting started

Navigate to the Manage repositories page.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930397090/gitserver-gitmgr-connect2git-sel.png?version=1&modificationDate=1630642822421&cacheVersion=1&api=v2)

<div align='center'><b>Figure 1:</b> Connect wizard start screen.</div>
<br>

To start integrating a git repository, follow the steps below:

1.  Click **Connect to Git Repository**. The connect repository wizard is displayed:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-start-screen(new).png?version=1&modificationDate=1630642823179&cacheVersion=1&api=v2&width=646&height=501)
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
        <div>
            Starting <b>v2.6.7+</b> of the Git Integration for Jira app, the default identities are not used and the repository is created without the additional key upload.
        </div>
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

## Settings

In the **Settings** screen, you can configure features such as [Smart Commits](/git-integration-for-jira-self-managed/smart-commits-docs/), [Repository Browser](/git-integration-for-jira-self-managed/repository-browser/) and [Project Permission](/git-integration-for-jira-self-managed/associating-project-permissions/) settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-cfg-screen.png?version=1&modificationDate=1630642823475&cacheVersion=1&api=v2&width=680&height=376)

<div align='center'>
    <b>Figure 2:</b> Settings screen at the end of the Connect wizard.</div>
<br>

*   **Smart Commits**  – Enable or disable this setting to allow processing of smart commits for this repository connection.

*   **Repository Browser** – Enable or disable this setting to allows users to view git repositories of configured projects via the **Git** menu on the Jira dashboard. This feature is only available on Jira Server/DC instances.

*   For _**Project Permissions**_, set one or more projects in the **Restrict to projects** field to map this repository and make the **Git Commits** tab available in the **Issue** pages of the associated projects. Otherwise, leave the _**Associate with all projects**_ state to <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2705.png' width=16 height=16 /> associate this repository to all projects.
<br>
<br>

The level of permissions can be one of the following:

<table>
    <thead>
        <tr>
            <td width=120><b>Level</b></td>
            <td><b>Process</b></td>
        </tr>
    </thead>
    <tbody>
        <tr valign='baseline'>
            <td><b>Repository</b></td>
            <td>
                <div>Select a repository from the repository list. For repositories inside integrations, view the integration then select a repository within <i>(<img valign='middle' src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ Show integration repositories)</i>. After the selection, you will be taken to the repository properties.</div>
                <p>Set the <b>Project Permissions</b> as follows:</p>                
                <ol>
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
                    Select an integration from the repository list then open the integration feature properties <i>(<img valign='middle' src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ Edit integration feature settings)</i>.
                </div>
                <p>Set the <b>Project Permissions</b> as follows:</p>
                <ol>
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
        For Project Permissions, the <b>View Development Tools</b> _project permission_ must be granted to Users ➜ Group ➜ <b><i>Project Roles</i></b>.
    </div>
    </div>
</div>

Click **Next**.

## HTTP(S) authentication

If the entered git clone URL requires HTTP credentials, the following screen appears:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-auth-scr-http(n).png?version=1&modificationDate=1630642824202&cacheVersion=1&api=v2&width=680&height=355)

<div align='center'>
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

## SSH authentication

For SSH git repository connections, the following screen is displayed for authentication:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930397090/gitserver-ssh-connect-auth-screen.png?version=1&modificationDate=1630642825404&cacheVersion=1&api=v2)

<div align='center'>
    <i><b>Figure 4:</b> SSH authentication screen in the Connect wizard.</i>
</div>
<br>

Upload the private key file by clicking **Choose File** and navigate to the private key file. Otherwise, paste the private key text into the provided box.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For establishing safety connection with SSH, upload a public Key to the SSH server and set the private Key to the SSH client.
        <div class='nextpara'>
            Take note that the SSH server is the Git server and the SSH client is the Jira server.
        </div>
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

## Passphrase Input

If the generated SSH key pair has a passphrase, you will see the following screen:

<img src='https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-auth-scr-pass.png?version=1&modificationDate=1630642824934&cacheVersion=1&api=v2&width=442&height=254' class='center img-responsive img-bordered' />

<div align='center'>
    <b>Figure 4:</b> SSH authentication screen in the Connect wizard.</div>
<br>

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

