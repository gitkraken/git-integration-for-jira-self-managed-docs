---

title: Enable/disable Repository Browser via git repository configuration page
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Enable/disable Repository Browser via git repository configuration page

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398739>

* * *

Access the Repository Browser via Jira dashboard menu Git ➜ **Repository browser** or alternatively, go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ _**Apps**_ ➜ _Git Integration for Jira_ _(sidebar)_ **➜ Repository browser**.

## Repository Browser settings

On the git repository configuration page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit** **integration/repository settings** to modify required repository settings. The _Advanced setup_ screen for configuring repositories is displayed.

Scroll down to the _**Repository Browser**_ section.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398739/git-viewer-configuration.png?version=1&modificationDate=1630642903809&cacheVersion=1&api=v2&width=680&height=226)

### **Repository Browser**

Select `Enabled` to activate this feature for this repository. Otherwise, set to `Disabled` to deactivate this feature for this repository.

### **Tags**

**Show all tags**  –  This will display all the tags for the specific issue.  
**Show tags matching the pattern**  –  This will display tags on issue pages that match the specified regular expression pattern.

|     |
| --- |
| _**For example:**_ |
| ```java<br>release2[.](7\|8)[.][0-9]+<br>``` |
| _This example is a filtering regexp for a range of releases from 2.7.x to 2.8.x. The sidebar will display git tags for release versions 2.7.0 to 2.8.x in descending order._ |

Click **Update** to save configuration changes for this repository.

[« Comparing branches/tags in Repository Browser](/wiki/spaces/GIJDC/pages/1930398705)

[Viewing commit code diffs »](/wiki/spaces/GIJDC/pages/1930398768/Viewing+commit+code+diffs)

### More related topics about repository browser

*   Page:
    
    [Repository Browser](/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Viewing list of commits in Repository Browser](/wiki/spaces/GIJDC/pages/1930398681/Viewing+list+of+commits+in+Repository+Browser) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Comparing branches/tags in Repository Browser](/wiki/spaces/GIJDC/pages/1930398705) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Enable/disable Repository Browser via git repository configuration page](/wiki/spaces/GIJDC/pages/1930398739) (Git Integration for Jira Data Center)