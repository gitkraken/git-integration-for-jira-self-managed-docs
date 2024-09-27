---

title: Associating project permissions
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Integrations and/or repositories can be associated with one or more Jira projects to restrict which users can view development information. All newly-connected repositories or integrations are associated with all Jira projects by default.

This feature is displayed on the following locations:

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>WIZARD</b> &nbsp;Add new integration wizard (_formerly Auto-connect wizard_) ➜ **Settings** screen.

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>WIZARD</b> &nbsp;Add new integration wizard (_formerly Auto-connect wizard_) ➜ **Settings** screen.

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>WIZARD</b> &nbsp;Connect to Git repository wizard (Connect wizard) ➜ **Settings** screen.

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>REPOSITORY</b> &nbsp;Manage Git Integration for Jira configuration page ➜ <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit repository settings**.

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>INTEGRATION</b> &nbsp;Manage Git Integration for Jira configuration page ➜ <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit integration feature settings**.

*   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>TRACKED FOLDER</b> &nbsp;Manage Git Integration for Jira configuration page ➜ <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit repository settings**.

&nbsp;

<img src='/wp-content/uploads/gij-gitserver-edit-feature-cfg-proj-acls.png' style='display:block;margin:25px auto;max-width:100%' />

**Restrict to projects**  –  One or more projects can be mapped to this repository or integration to make Git Commits tabs available in the Issue pages of the associated projects. Disable _**Associate with all projects**_ option to gain access to this field.

**Associate with all projects**  –  Enable this option to associate this repository or integration to all projects. Disable this option if you want to use the existing mapped projects from the **Restrict to projects** field. The default setting is enabled _(checked)_.

&nbsp;

### Project permissions level

There are several types of project permission levels, namely:

#### Repository level

<div class='embed-container' style='padding-bottom: 75.21%'>
    <iframe width='709' height='533' src='https://fast.wistia.com/embed/iframe/xvzj32nxou?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px;margin-bottom:30px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/xvzj32nxou'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

You can configure the project permissions for single connection repositories:

1.  On the git repository configuration page, click <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit repository settings**.

2.  On the page that appears, scroll down to **Project Permissions**.

3.  Uncheck (turn off) the **Associate with all projects** setting.

4.  Click on the **Restrict to projects** field then select one or more projects from the list.

5.  Click **Update** to save the settings.


The same process can also be applied for single repository connections in Jira Cloud.

### Integration level

<div class='embed-container' style='padding-bottom: 75.21%'>
    <iframe width='709' height='533' src='https://fast.wistia.com/embed/iframe/rnm5t639cz?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px;margin-bottom:30px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rnm5t639cz'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

You can configure the project permissions for integration (multiple repository connection):

1.  On the git repository configuration page, click <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit integration feature settings**.

2.  On the page that appears, scroll down to **Project Permissions**.

3.  Uncheck (turn off) the **Associate with all projects** setting.

4.  Click on the **Restrict to projects** field then select one or more projects from the list.

5.  Click **Update** to save the settings.


The same process can also be applied for integration connections in Jira Cloud -- <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit integration settings**.

### Repository level within integration

<div class='embed-container' style='padding-bottom: 75.21%'>
    <iframe width='709' height='533' src='https://fast.wistia.com/embed/iframe/rnm5t639cz?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px;margin-bottom:30px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/fder2qnpgw'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

You can configure the project permissions for repositories within integration:

1.  On the git repository configuration page, click <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Show integration repositories**. The Tracked folder dialog is displayed.

2.  Click a repository name to open its repository settings.

3.  On the page that appears, scroll down to **Project Permissions**.

4.  Uncheck (turn off) the **Associate with all projects** setting.

5.  Click on the **Restrict to projects** field then select one or more projects from the list.

6.  Click **Update** to save the settings.

&nbsp;
* * *

[**Prev:** Managing integration or repository configuration](/git-integration-for-jira-data-center/managing-repository-or-integration-configuration-gij-self-managed)

[**Next:** Bulk change](/git-integration-for-jira-data-center/bulk-change-gij-self-managed)

&nbsp;

### More related topics on setting up repositories

[Git integration configuration page](/git-integration-for-jira-data-center/git-integration-configuration-page-gij-self-managed)

[Using the Add new integration wizard](/git-integration-for-jira-data-center/using-the-add-new-integration-wizard-gij-self-managed)

[Using the Connect Repository wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed)

[Connecting a repository via Advanced setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed)

[Adding a repository hosted on Windows Server or Windows Network Share](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-server-or-windows-network-share-gij-self-managed)

[Setup repository root not located in Jira HOME directory](/git-integration-for-jira-data-center/setup-repository-root-not-located-in-jira-home-directory-gij-self-managed)

[Tracked folders overview](/git-integration-for-jira-data-center/tracked-folders-overview-gij-self-managed)

[Self-signed HTTPS integration](/git-integration-for-jira-data-center/self-signed-https-integration-gij-self-managed)

[Managing repository or integration configuration](/git-integration-for-jira-data-center/managing-repository-or-integration-configuration-gij-self-managed)

**Associating project permissions** (this page)

