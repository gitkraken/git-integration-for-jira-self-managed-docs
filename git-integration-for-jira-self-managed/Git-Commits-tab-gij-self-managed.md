---

title: Git Commits tab - Jira issue page
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The Git Commits tab shows commit information such as commit authors, date of commit, commit messages, access to view code diffs, commit id and view full commit.

<img src='/wp-content/uploads/gij-gitserver-git-commits-tab-enum.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

Open an issue then go to the _**Git Commits**_ tab to view commit information:

| Pointer | Information | Description |
| :--- | :--- | :--- |
| **1** | **Repository/Indexed** | Name of the repository _(as in app config)_ and date of last synchronization with remote repository. |
| **2** | **Author/Committer** | User who performed the commit. Hover the mouse pointer on the name to view user card. |
| **3** | **Issue key/Commit message** | This is the Jira issue with the corresponding commit message. |
| **4** | **Repository name and Branch name** | This is the name of the repository the commit has been made. Click to browse this repository via Repository Browser.<br><br>Adjacent to the repository name is the Git branch name. Click to view this branch via Repository Browser. |
| **5** | **Commit UUID** | UUID of the commit and git host link. Click the UUID to view the code diffs for this commit. Click the git host link to view this commit via the git host server. |
| **6** | **Open in GitKraken** | Opens and view this commit via the GitKraken client app. |
| **7** | **Commit indicator** | This is the commit indicator. Smart commit errors are also indicated here, if encountered. |
| **8** | **View full commit** | Click the **View Full Commit** button to view the full code diff for the selected commit. |
| **9** | **Web links** | These are clickable web links that will open the selected file code diff directly to git host portal in a new browser window/tab. |
| **10** | **Files changed** | List of files affected by the commit. Click the file or git host link to view code diff of this commit.<br><br><img src='/wp-content/uploads/gij-traffic-light-example.png' alt='Git commit traffic light example' width=117 height=16 style='display:block;margin:25px auto;max-width:100%' /><br><br>The traffic light indicator shows the added/modified/deleted lines from the file code diffs. |

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        View the whole commit code diff information by clicking the <b>View full commit</b> button to the right of the commit message.
        <p style='margin-bottom: 0px'>View code diff information of the particular file by clicking the filename for each file adjacent to the rollup counter markers.
        </p>
    </div>
    </div>
</div>
<br>

<p>&nbsp;</p>

<br>
<br>

[**Prev:** Git Roll Up tab](/git-integration-for-jira-data-center/git-roll-up-tab-docs-gij-self-managed)

[**Next:** Code syntax highlighter](/git-integration-for-jira-data-center/code-syntax-highlighter-gij-self-managed)


