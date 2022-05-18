---

title: View integration or repository properties
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397673/gitserver-gitmgr-view-details-01.png?version=1&modificationDate=1630642852300&cacheVersion=1&api=v2&width=550&height=190)

Click the view ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) icon to see basic git repository details for the selected integration/repository:

|     |     |
| --- | --- |
| **Column** | **Description** |
| _**Status**_ | This is the repository connection status.<br><br>*   It shows UPDATED if _Repository Root_ is configured correctly and the Jira instance can access it.<br>    <br>*   (JIRA SERVER DATA CENTER) It shows the DISABLED status if the connected repository is unchecked.<br>    <br>*   It shows REINDEXING, SCANNING or QUEUED during reindexing of the connected repository or tracked folder/repositories.<br>    <br>*   It shows ERROR if the connected repository has connection issues with the configured git host. |
| _**Last Indexed**_ | This is the date and time when synchronization was last executed. |
| _**Host URL**_ | Displays the host URL of the connected integration/repository. |
| _**Account**_ | This is shown for connected AWS integration. |
| _**Repository Root**_ | This is shown if a connected integration is a single repository.<br><br>This is the local path to the repository on the server where your Jira service is running. |
| _**Repository Origin**_ | This is shown if the connected integration is a single repository.<br><br>This is the URL to the hosted git service used on the project. |
| _**Changeset, File Added, File Modified, and File Deleted formats**_ | This is shown if the connected integration is a single repository and web linking is also configured.<br><br>Displays the web linking format strings _(if set in the repository web linking configuration)_. |



The displayed repositories can be sorted by clicking the corresponding list header. The Git Integration for Jira app will remember the sorting choice per user.

The Repository Browser will not display the repository if it is disabled in the Git Repositories configuration. The commits and code diffs in the **Issue** ➜ **Git Commits**, **Git Roll Up** and **Project** tabs will also be unavailable due to this.

[« SSL verify](/git-integration-for-jira-self-managed/SSL-verify)

[Viewing indexing logs »](/wiki/spaces/GIJDC/pages/1930397702/Viewing+indexing+logs)

### More related topics about managing repository/integration configuration

*   Page:

    [Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration) (Git Integration for Jira Data Center)

*   Page:

    [Managing integration via Actions](/wiki/spaces/GIJDC/pages/1930397476/Managing+integration+via+Actions) (Git Integration for Jira Data Center)

*   Page:

    [Show tracked or integration repositories](/wiki/spaces/GIJDC/pages/1930397507/Show+tracked+or+integration+repositories) (Git Integration for Jira Data Center)

*   Page:

    [Edit integration connection settings](/wiki/spaces/GIJDC/pages/1930397536/Edit+integration+connection+settings) (Git Integration for Jira Data Center)

*   Page:

    [Edit integration feature settings](/wiki/spaces/GIJDC/pages/1930397576/Edit+integration+feature+settings) (Git Integration for Jira Data Center)

*   Page:

    [SSL verify](/git-integration-for-jira-self-managed/SSL-verify) (Git Integration for Jira Data Center)

*   Page:

    [View integration or repository properties](/wiki/spaces/GIJDC/pages/1930397673/View+integration+or+repository+properties) (Git Integration for Jira Data Center)

*   Page:

    [Viewing indexing logs](/wiki/spaces/GIJDC/pages/1930397702/Viewing+indexing+logs) (Git Integration for Jira Data Center)

*   Page:

    [Removing integration or repository configuration](/wiki/spaces/GIJDC/pages/1930397738/Removing+integration+or+repository+configuration) (Git Integration for Jira Data Center)

*   Page:

    [Edit repository settings](/wiki/spaces/GIJDC/pages/1947107348/Edit+repository+settings) (Git Integration for Jira Data Center)