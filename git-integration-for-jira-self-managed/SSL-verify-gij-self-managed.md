---

title: SSL verify
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This feature can be accessed at the following locations on the Manage Git repositories page:

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>EXISTING INTEGRATION</b> <br>Actions ➜ **Edit integration connection settings**

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>EXISTING REPOSITORY</b> <br>Actions ➜ **Edit repositories settings** ➜ Repository Settings section

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW REPOSITORY</b> <br>Connect to Git repository ➜ **Advanced setup** ➜ Repository Settings section

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>EXISTING INTEGRATION</b> <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>EXISTING REPOSITORY</b> <br>Under **Repository/integration** _column_ ➜ click an integration or repository URL name

<br>
<hr>
<br>

The **SSL Verify** option is set to `Enabled` by default. If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.

![](/wp-content/uploads/gij-gitserver-integration-repo-settings-SSLv-sel.png)

<div align='center'><i>In the above example, the Integration Connection Settings screen from Git Integration <br>for Jira Server/Data Center is shown.</i></div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <b>SSL Verify</b> setting is available in Jira Server, Data Center and Jira Cloud. This option is not available for non-fetched repositories.
    </div>
    </div>
</div>

<br>
<br>

[Prev: Edit integration feature settings](/git-integration-for-jira-data-center/edit-integration-feature-settings-gij-self-managed)

[NexT: View integration or repository properties](/git-integration-for-jira-data-center/View-integration-or-repository-properties-gij-self-managed)

