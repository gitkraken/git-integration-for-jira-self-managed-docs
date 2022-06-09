---

title: Enable/disable Repository Browser via git repository configuration page
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Access the Repository Browser via Jira dashboard menu Git ➜ **Repository browser** or alternatively, go to Jira Administration ➜ _**Apps**_ ➜ _Git Integration for Jira_ _(sidebar)_ **➜ Repository browser**.

## Repository Browser settings

On the git repository configuration page, click &nbsp;<img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit** **integration/repository settings** to modify required repository settings. The _Advanced setup_ screen for configuring repositories is displayed.

Scroll down to the _**Repository Browser**_ section.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398739/git-viewer-configuration.png?version=1&modificationDate=1630642903809&cacheVersion=1&api=v2&width=680&height=226)

### **Repository Browser**

Select `Enabled` to activate this feature for this repository. Otherwise, set to `Disabled` to deactivate this feature for this repository.

### **Tags**

**Show all tags**  –  This will display all the tags for the specific issue.
**Show tags matching the pattern**  –  This will display tags on issue pages that match the specified regular expression pattern.

_**For example:**_<br>
```java<br>release2[.](7\|8)[.][0-9]+<br>```

_This example is a filtering regexp for a range of releases from 2.7.x to 2.8.x. The sidebar will display git tags for release versions 2.7.0 to 2.8.x in descending order._

Click **Update** to save configuration changes for this repository.

