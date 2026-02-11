---

title: Web linking
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The web linking feature adds links to your git hosting provider directly into the _**Git Commits**_ tab. Configure web linking options while adding/editing repository settings so that commits can include links to the git host pages.

<div class="bbb-callout bbb--tip">
    <div class="irow">
        <div class="ilogobox">
            <span class="logoimg"></span>
        </div>
        <div class="imsgbox">
            Web links are automatically configured for integrations connected via the Add new integration wizard (Auto-connect setup).
        </div>
    </div>
</div>

&nbsp;
* * *
&nbsp;

<div class='embed-container' style='padding-bottom:62.5%'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/zfxfemq7z8?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/zfxfemq7z8'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

### Supported git services

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

&nbsp;

### Web linking manual setup

<img src='/wp-content/uploads/gij-gitlab-guide-web-linking.png' style='display:block;margin:25px auto;max-width:100%' alt='GitLab web linking example'/>

Select a git host from the **Web Link** list. The web linking input box options are automatically filled out with corresponding variables for the selected git host. Change the variables according to the actual URL settings of the git host. Configure server and port and `${rev}` will be substituted based on the commit ID.

You can create several custom configuration to support other git hosting providers. The following five URLs should be configured for setup:

| Option | Description |
| :--- | :--- |
| _**Changeset Format**_ | This is the URL used to display revision.  <br>Use the following variable: `${rev}` – git revision |
| _**File Added Format,**_  <br>_**File Modified Format,**_  <br>_**File Deleted Format**_ | This is the URL to display content of added, modified or deleted files.<br>Use the following variables:<ul><li>`${num}` –  number of change (0, 1, …)</li><li>`${rev}`  –  git revision</li><li>`${path}` –  path of the file being changed</li><li>`${sha256path}`  –  sha256 applied to the path and hex encoded. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> in v4.17+ and is used in <b>GitHub.com</b> weblinking.</li><li>`${md5}`  –  md5 applied to the path and hex encoded. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> in v4.17+ and is used in <b>GitHub EE</b> weblinking.</li><li>`${sha1path}`  –  sha1 applied to the path and hex encoded. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> in v4.17+ and is used in <b>GitLab</b> weblinking.</li><li>`${parent}` –  parent git revision</li><li>`${blob}`  –  ID of blob object</li><li>`${parent_blob}` – ID of parent blob object</li><li>`$convert(${branch},"subStr","newSubStr")` – this inline function returns branch name with `subStr` replaced by a `newSubStr`.</li></ul><div class="bbb-callout bbb--info" style='margin-bottom:0px;'><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">The <code>${branch}</code> code has been changed to cope up with the character requirements on some hosting services.</div></div></div> |
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
        Some git hosts require web linking to be configured via the Git Integration app <b><i>Advanced Setup</i></b> or <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit integration/repository settings</b> screen.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
        <div class="ilogobox">
            <span class="logoimg"></span>
        </div>
        <div class="imsgbox">
            The Bonobo git server requires a branch name to construct URL. Use <code>$convert(${branch},"/","~2")</code> for web linking since bonobo requires substitution of <code>"/"</code> with <code>"~2"</code> in the branch name.
            <p style='margin-bottom:-10px !important'>
                <b>For example:</b><br>
                <code>http://&lt;host&gt;/Bonobo.Git.Server/Repository/&lt;project&gt;/$convert(${branch},"/","~2")/Commit/${rev}</code>
            </p>
        </div>
    </div>
</div>

Any Git host that is accessible via SSH, HTTP, HTTPS, git protocol, local and network share is supported.

Once properly configured, the **Git Commits** tab on the **Issues** page will display as follows:

<img src='/wp-content/uploads/gij-git-commits-clickable-web-links.png' style='display:block;margin:25px auto;max-width:100%' alt='Jira issue Git commits tab showing web links' />

The Git Integration app supports custom web linking. The commit information is displayed in the **Git Commits** issue tab if the git host server URL is provided on the **Web Linking** section in the [Advanced Setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup) or repository settings of the connected repositories.

&nbsp;
* * *

[**Prev:** General settings](/git-integration-for-jira-data-center/general-settings-docs-gij-self-managed)

[**Next:** Disabling Source and Commits tabs](/git-integration-for-jira-data-center/disabling-Source-and-Commits-tabs-gij-self-managed)

