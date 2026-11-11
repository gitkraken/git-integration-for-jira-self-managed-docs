---

title: Enable/disable Repository Browser via git repository configuration page
description: Turn the Repository Browser on or off for a repository and choose which tags it shows from the repository settings page.
product: Git Integration for Jira Data Center
feature: Repository Browser
content_type: how-to
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [repository browser, repository settings, tags, regex pattern, enable, disable]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Enable/disable Repository Browser via git repository configuration page"
    nav_order: 30
    nav_parent: "repository-browser-gij-self-managed"
    page_type: "content"
    card_icon: "folder-open"
    card_color: "blue"
    card_description: "Turn the Repository Browser on or off for a repository and choose which tags it shows from the repository settings page"
---

Access the Repository Browser via Jira dashboard menu Git ➜ **Repository browser** or alternatively, go to Jira Administration ➜ _**Apps**_ ➜ _Git Integration for Jira_ _(sidebar)_ ➜ **Repository browser**.

&nbsp;

### Repository Browser settings

On the git repository configuration page, click &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit** **integration/repository settings** to modify required repository settings. The _Advanced setup_ screen for configuring repositories is displayed.

Scroll down to the _**Repository Browser**_ section.

<img src='/wp-content/uploads/gij-git-viewer-configuration.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

#### Repository Browser

Select `Enabled` to activate this feature for this repository. Otherwise, set to `Disabled` to deactivate this feature for this repository.

&nbsp;

#### Tags

**Show all tags**  –  This will display all the tags for the specific issue.
**Show tags matching the pattern**  –  This will display tags on issue pages that match the specified regular expression pattern.

_**For example:**_<br>
```java
release2[.](7\|8)[.][0-9]+
```

_This example is a filtering regexp for a range of releases from 2.7.x to 2.8.x. The sidebar will display git tags for release versions 2.7.0 to 2.8.x in descending order._

Click **Update** to save configuration changes for this repository.

&nbsp;
* * *

[**Prev:** Comparing branches/tags in Repository Browser](/git-integration-for-jira-data-center/comparing-branches-tags-in-repository-browser-gij-self-managed)

[**Next:** Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed)


