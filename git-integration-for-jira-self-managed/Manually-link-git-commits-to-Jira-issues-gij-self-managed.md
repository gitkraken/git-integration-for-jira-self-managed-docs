---

title: Manually link git commits to Jira issues
description: "Manually add, edit or remove the Jira issues associated with a git commit using the Change commit issues dialog."
product: Git Integration for Jira Data Center
feature: Linking Commits to Issues
content_type: how-to
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator, Project Administrator]
version_required: all
status: GA
last_verified: 2023-08
llms_include: true
tags: [change commit issues, commit association, issue keys, view full commit, reindex]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Manually link git commits to Jira issues"
    nav_order: 10
    nav_parent: "linking-git-commits-to-jira-issues-gij-self-managed"
    page_type: "content"
    card_icon: "link"
    card_color: "blue"
    card_description: "Manually add, edit or remove the Jira issues associated with a git commit using the Change commit issues dialog"
---

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/cq3r68b9ou?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/cq3r68b9ou'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

> **Warning:** The process steps in this section applies to Jira Server/Data Center/Cloud with installed Git Integration for Jira app.

To manually link a git commit to a Jira issue, access the **Change commit issues** feature from the following locations:

*   **Project page** ➜ Git Commits ➜ click _View Full Commit_ on the commit panel.

*   **Issue page** ➜ Git Commits tab ➜ click _View Full Commit_ on the commit panel.

*   **Git menu** ➜ View all repositories ➜ click a repository with git commits.


![View full commits dialog highlighting the change commit issues function](/wp-content/uploads/gij-gitserver-view-full-commits-assoc.png)

Click the **Change commit issues** label. The following dialog is displayed.

<img src='/wp-content/uploads/gij-gitserver-view-full-commits-assoc-issue-dlg.png' width=566 height=283 style='display:block;margin:25px auto;max-width:100%' alt='This is the commit association dialog where you can manually map or associate a commit to a Jira issue. The setting shows one Jira issue key association.' />

Add, edit or delete linked Jira issue keys in the _**Associated issues to commit**_ field.

*   JIRA administrators can add/remove any association.

*   Project administrators can add/remove any association in that project.

*   The authors of the commit can add/remove the association, if they have the View Development Tools access.


If the commit is associated with multiple Jira issues, you will see the following:

<img src='/wp-content/uploads/gij-gitserver-view-full-commits-assoc-issue-dlg-multi.png' width=566 height=283 style='display:block;margin:25px auto;max-width:100%' alt='This is the commit association dialog where you can manually map or associate a commit to a Jira issue. The setting shows multiple Jira issue key associations.' />

<br>

In the above example, the selected commit is associated with Jira issues `TEST-1`, `TEST-2` and `PROJ-4` separated by commas.

Using the above example:

*   To associate the commit to an issue, insert a new issue key separated by a comma.

*   To remove commit association to an issue, delete the issue key.


Click **Save** to save the changes.

> **Info:** Saving the changes triggers a repository reindexing to show new associations.

&nbsp;
* * *

[**Prev:** Linking git commits to Jira issues](/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed)

[**Next:** Git notes](/git-integration-for-jira-data-center/git-notes-gij-self-managed)


