---

title: Git notes
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Git Integration for Jira app displays <a href='https://git-scm.com/docs/git-notes' target='_blank'>git notes</a> in the **Git Commits** tab:

<img src='/wp-content/uploads/gij-gitserver-dc-git-notes-sample.png' width=557 height=289 style='display:block;margin:25px auto;max-width:100%' />

<br>

For a git repository with several existing commits in it, commit authors can associate issue keys via git notes to these commits without having to edit the commit messages. The Git Integration for Jira app will index issue keys in git notes.

Smart commit actions are also supported in git notes.

Each commit can only have one git note per namespace. There can be multiple note namespaces per commit. These note namespaces are automatically indexed.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Git notes are sorted by name.
    </div>
    </div>
</div>
<br>

**Guidelines for adding new git notes:**

*   add git notes to new commits which has not been indexed yet;

*   git notes can be added to old commits which is already indexed – but does not have an issue key.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For old commits that are already indexed and have issue key(s) in commit message - see <a href='/git-integration-for-jira-data-center/how-do-i-clear-the-git-integration-for-jira-app-cache-manually-gij-self-managed'>How do I clear the Git Integration Plugin for Jira cache manually?</a> FAQ article.
    </div>
    </div>
</div>
<br>

```powershell
git notes add -m 'TST-3 is also fixed' 107af254
git show -s 107af254
git push origin refs/notes/*
```

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        GitHub and GitLab don't display Git notes. However, notes can be fetched from and pushed to both services.
    </div>
    </div>
</div>
<br>

## Bonus: Adding git notes with TortoiseGit

For those who are using TortoiseGit client on Windows, you can perform the following steps to add/edit git notes:

1.  Navigate to your local git clone folder.

    ![](/wp-content/uploads/gij-tortoisegit-bonus-git-notes-example-c.png)

2.  Right click anywhere on the file list view pane of the File Explorer to open up the context menu; go to **TortoiseGit** then click **Show log**. The Log Messages dialog is displayed.

    ![](/wp-content/uploads/gij-tortoisegit-bonus-git-notes-show-log-dlg-c.png)

3.  Right click on a commit or PR then click **Edit notes**. The Edit Notes dialog is displayed.

    ![](/wp-content/uploads/gij-tortoisegit-bonus-git-notes-edit-notes-dlg-c.png)

    *   Enter a descriptive note for the selected commit or PR. _We recommend to add a Jira issue key to this git note so that it will be indexed by the Git Integration for Jira app._

    *   Click **OK** to accept this entry.

4.  Push this git note to the git server. To do so, right click on the file list view of the File Explorer then click **Git sync…** . The GIt Synchronization dialog is displayed.

    ![](/wp-content/uploads/gij-tortoisegit-bonus-git-notes-git-sync-push-notes-c.png)

5.  The new/edited git note is pushed to the git server and the git note can be seen in the Git Commits tab of the specified Jira issue.

<br>

<img src='/wp-content/uploads/gij-gitserver-dc-git-notes-sample.png' width=550 height=286 style='display:block;margin:25px auto;max-width:100%' />

<p>&nbsp;</p>

<br>
<br>

[**Prev:** Manually link git commits to Jira issues](/git-integration-for-jira-data-center/manually-link-git-commits-to-jira-issues-gij-self-managed)

[**Next:** Smart commits](/git-integration-for-jira-data-center/smart-commits-gij-self-managed)


