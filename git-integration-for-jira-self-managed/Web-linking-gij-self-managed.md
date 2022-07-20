---

title: Web linking
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The web linking feature adds links to your git hosting provider directly into the _**Git Commits**_ tab. Configure web linking options while adding/editing repository settings so that commits can include links to the git host pages.

Web links are automatically configured for integrations connected via the Add new integration wizard (Auto-connect).

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/qmumdo048n?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/qmumdo048n'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

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

<br>

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398212/gitlab-guide-web-linking.png?version=1&modificationDate=1630642879210&cacheVersion=1&api=v2&width=680&height=318)

Select a git host from the **Web Link** list. The web linking input box options are automatically filled out with corresponding variables for the selected git host. Change the variables according to the actual URL settings of the git host. Configure server and port and `${rev}` will be substituted based on the commit ID.

You can create several custom configuration to support other git hosting providers. The following five URLs should be configured for setup:

| Option | Description |
| :--- | :--- |
| _**Changeset Format**_ | This is the URL used to display revision.  <br>Use the following variable: `${rev}` – git revision |
| _**File Added Format,**_  <br>_**File Modified Format,**_  <br>_**File Deleted Format**_ | This is the URL to display content of added, modified or deleted files.  <p>Use the following variables:</p><ul><li>`${num}` –  number of change (0, 1, …)</li><li>`${rev}`  –  git revision</li><li>`${path}` –  path of the file being changed</li><li>`${parent}` –  parent git revision</li><li>`${blob}`  –  ID of blob object</li><li>`${parent_blob}` – ID of parent blob object</li><li>`$convert(${branch},"subStr","newSubStr")` – this inline function returns branch name with `subStr` replaced by a `newSubStr`.</li></ul>The `${branch}` code has been changed to cope up with the character requirements on some hosting services. |
| _**View Format**_ | _String._ Optional. <br><br>This URL is unused and not being configured for the newly added integration types. |

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app supports an unlimited number of repositories.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Some git hosts require web linking to be configured via the Git Integration app _**Advanced Setup**_ or Actions ➜ **Edit integration/repository settings** screen.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Bonobo git server requires a branch name to construct URL.  Use <code>$convert(${branch},"/","~2")</code> for web linking since bonobo requires substitution of "/" with "~2" in the branch name.
        <div class="nextpara>
            <b>For example:</b><br>
            <code>http://<host>/Bonobo.Git.Server/Repository/<project>/$convert(${branch},"/","~2")/Commit/${rev}</code>
        </div>
    </div>
    </div>
</div>

Any Git host that is accessible via SSH, HTTP, HTTPS, git protocol, local and network share is supported.

Once properly configured, the **Git Commits** tab on the **Issues** page will display as follows:

![Jira issue Git commits tab showing web links](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398212/git-commits-clickable-web-links.png?version=1&modificationDate=1630642879449&cacheVersion=1&api=v2&width=557&height=261)

The Git Integration app supports custom web linking. The commit information is displayed in the **Git Commits** issue tab if the git host server URL is provided on the **Web Linking** section in the [Advanced Setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup/) or repository settings of the connected repositories.

