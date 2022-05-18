---

title: Web linking
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The web linking feature adds links to your git hosting provider directly into the _**Git Commits**_ tab. Configure web linking options while adding/editing repository settings so that commits can include links to the git host pages.

Web links are automatically configured for integrations connected via the Auto-connect wizard.

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/qmumdo048n) _to open this video in a new browser tab for more viewing options._


The following providers are supported:

*   **cgit**

*   **Fisheye**

*   **GitHub**

*   **Gitorious**

*   **gitweb**

*   **Beanstalk**

*   **CloudForge**

*   **Atlassian Stash**

*   **GitLab**

*   **TFS (starting v2013)**

*   **Azure Server**

*   **VSTS**

*   **Azure DevOps**

*   **Gerrit**

*   **Bonobo**

*   **AWS CodeCommit**

*   **Bitbucket**

*   **Bitbucket Server**

*   **Gitblit**

*   **Gitolite**


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398212/gitlab-guide-web-linking.png?version=1&modificationDate=1630642879210&cacheVersion=1&api=v2&width=680&height=318)

Select a git host from the **Web Link** list. The web linking input box options are automatically filled out with corresponding variables for the selected git host. Change the variables according to the actual URL settings of the git host. Configure server and port and `${rev}` will be substituted based on the commit ID.

You can create several custom configuration to support other git hosting providers. The following five URLs should be configured for setup:

|     |     |
| --- | --- |
| **Option** | **Description** |
| _**Changeset Format**_ | This is the URL used to display revision.  <br>Use the following variable: `${rev}`  – git revision |
| _**File Added Format,**_  <br>_**File Modified Format,**_  <br>_**File Deleted Format**_ | This is the URL to display content of added, modified or deleted files.  <br>Use the following variables:<br><br>*   `${num}` –  number of change (0, 1, …)<br>    <br>*   `${rev}`  –  git revision<br>    <br>*   `${path}`  –  path of the file being changed<br>    <br>*   `${parent}`  –  parent git revision<br>    <br>*   `${blob}`  –  ID of blob object<br>    <br>*   `${parent_blob}`  –  ID of parent blob object<br>    <br>*   `$convert(${branch},"subStr","newSubStr")`  –  this inline function returns branch name with `subStr` replaced by a `newSubStr`. As of **v2.11.0+** of the Git Integration app, the `${branch}` code has been changed to cope up with the character requirements on some hosting services. |
| _**View Format**_ | _String._ Optional. <br><br>This URL is unused and not being configured for the newly added integration types. |

The **Git Integration for Jira** app supports an unlimited number of repositories.

Some git hosts require web linking to be configured via the Git Integration app _**Advanced Setup**_ or Actions ➜ **Edit integration/repository settings** screen.

The Bonobo git server requires a branch name to construct URL.  Use `$convert(${branch},"/","~2")` for web linking since bonobo requires substitution of "/" with "~2" in the branch name.

**For example:**
`http://<host>/Bonobo.Git.Server/Repository/<project>/$convert(${branch},"/","~2")/Commit/${rev}`


Any Git host that is accessible via SSH, HTTP, HTTPS, git protocol, local and network share is supported.

Once properly configured, the **Git Commits** tab on the **Issues** page will display as follows:

![Jira issue Git commits tab showing web links](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398212/git-commits-clickable-web-links.png?version=1&modificationDate=1630642879449&cacheVersion=1&api=v2&width=557&height=261)

The Git Integration app supports custom web linking. The commit information is displayed in the **Git Commits** issue tab if the git host server URL is provided on the **Web Linking** section in the [Advanced Setup](/wiki/spaces/GIJDC/pages/1930397180/Connecting+a+repository+via+Advanced+setup) or repository settings of the connected repositories.

[« General settings](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398111/%28GDC%29+General+settings)

[Disabling Source and Commits tabs »](/wiki/spaces/GIJDC/pages/1930398249/Disabling+Source+and+Commits+tabs)