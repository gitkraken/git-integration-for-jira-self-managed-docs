---

title: Permissions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
VERSION 4.0+ We are dropping support for Jira 7.x.x.

VERSION 2.13.0+ We are dropping support for Java 7, Jira 6.3 and 6.4.

VERSION 3.5.1+ Dropped support for Internet Explorer 11 browser.

**Universal Plugin Manager 2.2** or later is required to properly install this app.

## Permissions Requirement to Display Commit Information

_Right click_ [_here_](https://bigbrassband.wistia.com/medias/ynjggc2wzg) _to open this video in a new browser tab for more viewing options._

Users must have ‘_**View Development Tools**_’ permission in order to view commit information on the issue page.

Administrators must grant themselves the ‘_**View Development Tools**_’ permission in order to view commit information on the issue pages.


The user needs to be in the developers group to view code diffs when default permission scheme is used.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/408453129/view-dev-tools-project-acl(c).png?version=1&modificationDate=1585809947043&cacheVersion=1&api=v2&width=680&height=361)

Consider the following criteria when setting permissions:

*   Permission name may be different depending on your version of Jira.

*   Project permissions are configured on the project administration page. Different projects may have different permissions.

*   Default permission scheme grants access to add-on to all members of _**administrators**_ and _**developers**_ groups. No additional configuration is required in this case.