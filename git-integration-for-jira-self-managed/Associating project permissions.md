---

title: Associating project permissions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Integrations and/or repositories can be associated with one or more Jira projects to restrict which users can view development information. All newly-connected repositories or integrations are associated with all Jira projects by default.

This feature is displayed on the following locations:

*   WIZARD &nbsp;Add new integration wizard (_formerly Auto-connect wizard_) ➜ **Settings** screen.

*   **WIZARD** &nbsp;Add new integration wizard (_formerly Auto-connect wizard_) ➜ **Settings** screen.

*   **WIZARD** &nbsp;Connect to Git repository wizard (Connect wizard) ➜ **Settings** screen.

*   **REPOSITORY** &nbsp;Manage Git Integration for Jira configuration page ➜ <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit repository settings**.

*   **INTEGRATION** &nbsp;Manage Git Integration for Jira configuration page ➜ <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration feature settings**.

*   **TRACKED FOLDER** &nbsp;Manage Git Integration for Jira configuration page ➜ <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit repository settings**.

<br>

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397766/gitserver-edit-feature-cfg-proj-acls.png?version=1&modificationDate=1639569436677&cacheVersion=1&api=v2&width=680&height=155)

**Restrict to projects**  –  One or more projects can be mapped to this repository or integration to make Git Commits tabs available in the Issue pages of the associated projects. Disable _**Associate with all projects**_ option to gain access to this field.

**Associate with all projects**  –  Enable this option to associate this repository or integration to all projects. Disable this option if you want to use the existing mapped projects from the **Restrict to projects** field. The default setting is enabled _(checked)_.

## Project permissions level

There are several types of project permission levels, namely:

### Repository level

<div class='embed-container' style='padding-bottom: 75.21%'>
    <iframe width='709' height='533' src='https://fast.wistia.com/embed/iframe/xvzj32nxou?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/xvzj32nxou'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

You can configure the project permissions for single connection repositories:

1.  On the git repository configuration page, click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit repository settings**.

2.  On the page that appears, scroll down to **Project Permissions**.

3.  Uncheck (turn off) the **Associate with all projects** setting.

4.  Click on the **Restrict to projects** field then select one or more projects from the list.

5.  Click **Update** to save the settings.


The same process can also be applied for single repository connections in Jira Cloud.

### Integration level

<div class='embed-container' style='padding-bottom: 75.21%'>
    <iframe width='709' height='533' src='https://fast.wistia.com/embed/iframe/rnm5t639cz?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rnm5t639cz'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

You can configure the project permissions for integration (multiple repository connection):

1.  On the git repository configuration page, click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration feature settings**.

2.  On the page that appears, scroll down to **Project Permissions**.

3.  Uncheck (turn off) the **Associate with all projects** setting.

4.  Click on the **Restrict to projects** field then select one or more projects from the list.

5.  Click **Update** to save the settings.


The same process can also be applied for integration connections in Jira Cloud -- <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration settings**.

### Repository level within integration

<div class='embed-container' style='padding-bottom: 75.21%'>
    <iframe width='709' height='533' src='https://fast.wistia.com/embed/iframe/rnm5t639cz?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/fder2qnpgw'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

You can configure the project permissions for repositories within integration:

1.  On the git repository configuration page, click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Show integration repositories**. The Tracked folder dialog is displayed.

2.  Click a repository name to open its repository settings.

3.  On the page that appears, scroll down to **Project Permissions**.

4.  Uncheck (turn off) the **Associate with all projects** setting.

5.  Click on the **Restrict to projects** field then select one or more projects from the list.

6.  Click **Update** to save the settings.

