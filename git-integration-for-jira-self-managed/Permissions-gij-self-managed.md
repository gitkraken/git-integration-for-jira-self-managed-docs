---

title: Permissions
description: "Learn which Jira permissions, such as View Development Tools, users need to see commit information and code diffs on Jira issues."
product: Git Integration for Jira Data Center
feature: Permissions
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-08
llms_include: true
tags: [permissions, view development tools, permission scheme, developers group, code diffs]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "permissions-gij-self-managed"
    nav_label: "Permissions"
    nav_order: 50
    nav_parent: ""
    page_type: "content"
---

> **Warning:** <b>Depreciation notes</b>
> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.0+</b> -- We are dropping support for Jira 7.x.x.<br>
> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 3.5.1+</b> -- Dropped support for Internet Explorer 11 browser.<br>
> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 2.13.0+</b> -- We are dropping support for Java 7, Jira 6.3 and 6.4.

> **Info:** <b>Universal Plugin Manager 2.2</b> or later is required to properly install this app.

&nbsp;

### Permissions Requirement to Display Commit Information

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/ynjggc2wzg?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:12px;margin-bottom:30px;'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/ynjggc2wzg'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

> **Warning:** Users must have ‘<b><i>View Development Tools</i></b>’ permission in order to view commit information on the issue page.
> <div class="nextpara">
> Administrators must grant themselves the ‘<b><i>View Development Tools</i></b>’ permission in order to view commit information on the issue pages.</div>

The user needs to be in the developers group to view code diffs when default permission scheme is used.

![](/wp-content/uploads/gij-docs-permissions-view-dev-tools-project-acl-c.png)

Consider the following criteria when setting permissions:

*   Permission name may be different depending on your version of Jira.

*   Project permissions are configured on the project administration page. Different projects may have different permissions.

*   Default permission scheme grants access to add-on to all members of _**administrators**_ and _**developers**_ groups. No additional configuration is required in this case.

