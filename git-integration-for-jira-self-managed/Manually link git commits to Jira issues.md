---

title: Manually link git commits to Jira issues
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/cq3r68b9ou) _to open this video in a new browser tab for more viewing options._

The process steps in this section applies to Jira Server/Cloud with installed Git Integration for Jira app.


To manually link a git commit to a Jira issue, access the **Change commit issues** feature from the following locations:

*   **Project page** ➜ Git Commits ➜ click _View Full Commit_ on the commit panel.

*   **Issue page** ➜ Git Commits tab ➜ click _View Full Commit_ on the commit panel.

*   **Git menu** ➜ View all repositories ➜ click a repository with git commits.


![View full commits dialog highlighting the change commit issues function](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398296/gitserver-view-full-commits-assoc.png?version=1&modificationDate=1630642883212&cacheVersion=1&api=v2&width=680&height=375)

Click the **Change commit issues** label. The following dialog is displayed.

![This is the commit association dialog where you can manually map or associate a commit to a Jira issue. The setting shows one Jira issue key association.](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398296/gitserver-view-full-commits-assoc-issue-dlg.png?version=1&modificationDate=1630642882967&cacheVersion=1&api=v2&width=566&height=283)

Add, edit or delete linked Jira issue keys in the _**Associated issues to commit**_ field.

*   JIRA administrators can add/remove any association.

*   Project administrators can add/remove any association in that project.

*   The authors of the commit can add/remove the association, if they have the View Development Tools access.



If the commit is associated with multiple Jira issues, you will see the following:

![This is the commit association dialog where you can manually map or associate a commit to a Jira issue. The setting shows multiple Jira issue key associations.](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398296/gitserver-view-full-commits-assoc-issue-dlg-multi.png?version=1&modificationDate=1630642882718&cacheVersion=1&api=v2&width=566&height=283)

In the above example, the selected commit is associated with Jira issues `TEST-1`, `TEST-2` and `PROJ-4` separated by commas.

Using the above example:

*   To associate the commit to an issue, insert a new issue key separated by a comma.

*   To remove commit association to an issue, delete the issue key.


Click **Save** to save the changes.

Saving the changes triggers a repository reindexing to show new associations.

[« Linking git commits to Jira issues (index)](/wiki/spaces/GIJDC/pages/1930398265/Linking+git+commits+to+Jira+issues)

[Git notes »](/git-integration-for-jira-self-managed/Git-notes)

