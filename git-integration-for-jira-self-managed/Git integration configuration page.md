---

title: Git integration configuration page
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-manage-git-repo-screen.png?version=1&modificationDate=1630642814252&cacheVersion=1&api=v2)

On this page, you will be able to setup your git repositories and connect them to Jira via Manage git repositories page. Utilize the following features for git integration and configuration:

* * *

|     |
| --- |
| ### Add new integration panel |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-auto-connect-panel.png?version=1&modificationDate=1630642814741&cacheVersion=1&api=v2) |
| Formerly known as Auto-Connect integration panel.<br><br>In here, you will find special integration options for specific git hosts. This feature supports multiple connected repositories and automates git integration.<br><br>We highly recommend this feature for multiple repository configuration.<br><br>For more details on supported git hosts, see the Auto-connect section in our [Integration guides](/wiki/spaces/GIJDC/pages/92176395/Integration+Guides).<br><br>The **Add tracked folder** connection feature is added to the **Add new integration** panel for easy access.<br><br>**GitLab**  <br>We are dropping support for Gitlab API v3. Please use **GitLab API v4** when adding new integrations for increased security. |

|     |
| --- |
| ### Connect to Git repository |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-connect-git-repo.png?version=1&modificationDate=1630642815446&cacheVersion=1&api=v2) |
| This feature opens the Connect wizard.<br><br>You can connect single git repositories using this setup such as git protocol, SSH, HTTP/HTTPS, etc. Clicking the adjacent **…** will open the dropdown list of integration options such as [Add tracked folder](/wiki/spaces/GIJDC/pages/91947120/Tracked+Folders) and equivalent integration connection options. |

|     |
| --- |
| ### Enable all or Disable all |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-enable-disable-all.png?version=1&modificationDate=1630642815698&cacheVersion=1&api=v2) |
| The **Enable all** function will enable each integration in the repository list and mark all checkboxes in the _**Enabled**_ column. The **Disable all** function will disable each integration in the repository list and unmark all the checkboxes in the _**Enabled**_ column. |

|     |
| --- |
| ### Bulk change |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-bulk-change.png?version=1&modificationDate=1630642815933&cacheVersion=1&api=v2) |
| Bulk change provides an easier way to import or export repository configuration. This feature is useful when you are migrating from an old server to a new server and is also recommended when upgrading to a new version of Git Integration for Jira app.<br><br>**Export Configuration**  – this function will export your repository integration configuration to a tab-delimited file (.TSV).<br><br>**Import Configuration**  – this function will import your repository integration configuration from a tab-delimited file (.TSV).<br><br>For more information, see [Bulk change](/wiki/spaces/GIJDC/pages/1930397801/Bulk+change). |

|     |
| --- |
| ### Reindex all |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-reindex-all.png?version=1&modificationDate=1630642816165&cacheVersion=1&api=v2) |
| This function will perform a reindex queue of all integration in the repository list. Disabled integrations are ignored.<br><br>For more information on this topic, see [Reindexing](/wiki/spaces/GIJDC/pages/1930399289/Reindexing). |

|     |
| --- |
| ### Webhooks |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-webhooks-sidebar.png?version=1&modificationDate=1630642817385&cacheVersion=1&api=v2) |
| Opens the Webhooks configuration page. Enable/disable webhooks to trigger immediate reindex of the connected git repositories and integration.<br><br>For more information about this topic, click [here](/wiki/spaces/GIJDC/pages/1930399378/Integration+webhooks) to go to the **Webhooks documentation page**. |

### Related helpful tips

**SSH**
When setting up repositories with the Git Integration app, you need to have the necessary access permissions on the private key on the Git server to proceed.

**Windows Server**
For cases when git repositories are hosted at Windows servers (Windows Server network drive) — while it is using the Windows server networking, the network credentials accessing the git repository must be the same as the user running Jira.

**Windows Network Share**
When using Windows network sharing for the repository origin, it is recommended to allocate repositories’ paths shorter than 256 characters.

Example: `\\WS129\custom-repo\project-z\`

Otherwise, the provided URL will not be recognized as valid.

**For Jira hosted on Windows**
When using Active Directory accounts for repository access, changing the password of the AD account running Jira can cause repository authentication issues.

The solution for this is to restart Jira to regain access to repositories.

**Repository REST API**
As of **v2.8.3+** of the Git Integration for Jira app, the REST API for managing repositories are implemented. The documentation for this feature is available at [Repository REST API](/wiki/spaces/GITSERVER/pages/265846822/Repository+API).

**Integration REST API**
As of **v3.5.0.2+** of the Git Integration for Jira app, the REST API for managing integrations are implemented. The documentation for this feature is available at [Integration REST API](/wiki/spaces/GITSERVER/pages/360808449/Integration+API).

[« Setting up repositories (index)](/wiki/spaces/GIJDC/pages/1930396906/Setting+up+repositories)

[Using the Add new integration wizard »](/wiki/spaces/GIJDC/pages/1930397044/Using+the+Add+new+integration+wizard)

### More related topics about setting up repositories

*   Page:

    [Git integration configuration page](/wiki/spaces/GIJDC/pages/1930396951/Git+integration+configuration+page) (Git Integration for Jira Data Center)

*   Page:

    [Using the Add new integration wizard](/wiki/spaces/GIJDC/pages/1930397044/Using+the+Add+new+integration+wizard) (Git Integration for Jira Data Center)

*   Page:

    [Using the Connect Repository wizard](/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard) (Git Integration for Jira Data Center)

*   Page:

    [Connecting a repository via Advanced setup](/wiki/spaces/GIJDC/pages/1930397180/Connecting+a+repository+via+Advanced+setup) (Git Integration for Jira Data Center)

*   Page:

    [Adding a repository hosted on Windows Server or Windows Network share](/wiki/spaces/GIJDC/pages/1930397287/Adding+a+repository+hosted+on+Windows+Server+or+Windows+Network+share) (Git Integration for Jira Data Center)

*   Page:

    [Setup repository root not located in Jira Home directory](/wiki/spaces/GIJDC/pages/1930397313/Setup+repository+root+not+located+in+Jira+Home+directory) (Git Integration for Jira Data Center)

*   Page:

    [Tracked folders overview](/wiki/spaces/GIJDC/pages/1930397330/Tracked+folders+overview) (Git Integration for Jira Data Center)

*   Page:

    [Self-signed HTTPS integration](/wiki/spaces/GIJDC/pages/1930397349/Self-signed+HTTPS+integration) (Git Integration for Jira Data Center)

*   Page:

    [Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration) (Git Integration for Jira Data Center)

*   Page:

    [Associating project permissions](/wiki/spaces/GIJDC/pages/1930397766/Associating+project+permissions) (Git Integration for Jira Data Center)