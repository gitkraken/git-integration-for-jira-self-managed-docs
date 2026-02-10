---

title: Ways to Index Git Data to Jira Issues
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

There are several ways to associate git data to Jira issues:

| Objective | Method/Trigger | Description | Example | Video |
| :--- | :--- | :--- | :--- | :--- |
| Link commit to Jira issue | Commit message | Commit by a Jira key in the commit message. | "TEST-1 add fix for bug" | [vid link](https://gitkraken.wistia.com/medias/7kj43knu4m) |
| Link commit to Jira issue | Git note | Commit by a Jira key in git notes to the commit. | \-  | \-  |
| Associate commit to Jira issue | Change commit issues\` in the \`Commits\` tab of a repository in the Repository Browser | Associate git commit(s) to Jira issue via Commits tab of a repository in the Repository Browser. | TEST-1, TEST-4 | \-  |
| Associate commit to Jira issue | Change commit issues in the View full commit dialog of the selected commit in Commits tab | Associate git commits to Jira issue via View full commit dialog in Commits tab. | TEST-1, TEST-4 | \-  |
| Link commits to Jira issue | Pull/merge request | PR/MR Jira key in the pull/merge request comment. | "Merge branch 1.5.1-a6b4c1d5e3f2 to TEST-1 when bug is fixed." | \-  |
| Link branch to Jira issue | Commit message | Adding a Jira key in the branch name. | "TEST-1-add-fix-for-bug" | \-  |
| Link branch to Jira issue | Associated git commits | The branch commit is already associated to the Jira issue. | "TEST-1-add-fix-for-bug" | \-  |
| Link pull/merge request to a Jira issue | Pull Request | Merge/Pull request by a Jira key in the MRs/PRs name. | "TEST-1 merge branch add fix for bug" | \-  |
| Link pull/merge request to a Jira issue | Add a description to a PR/MR after creation via the git service web portal | Merge/Pull request by a Jira key in the MRs/PRs description in the git service web portal | "This branch from this pull/merge request will be merged to TEST-1" | \-  |
| Link pull/merge request to Jira issue | Associated git commits | Merge/Pull request if the MR/PR commits are already associated. | A commit in the PR/MR is already linked to TEST-1 | \-  |
| Link pull/merge request to Jira issue | Associated git commits | Merge/Pull request by a Jira key in the MRs/PRs base or compare branch. | \-  | \-  |
| Tag a commit | Associated tags in a Jira issue. (See example) | Associated tags in a Jira issue.  <br>Tags are associated only with a Jira issue by Jira keys that are specified in commits that belong to the tag.<br><br>**Note:** Specifying a Jira key in the name of a tag does NOT associate this tag with the mentioned Jira issue. | $ git tag -a v3.7 9f1a4c2 | \-  |

&nbsp;

### Manually associate git commits to Jira issues

For more information on this topic, see documentation [Associate git commit to Jira issues manually](/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed).

### More How-to articles

[How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed/)

[Setting Project Permissions](/git-integration-for-jira-data-center/Setting-Project-Permissions-gij-self-managed)

[How to create a HAR file and send it to support for analysis](/git-integration-for-jira-data-center/how-to-create-a-har-file-and-send-it-to-support-for-analysis-gij-self-managed/)

[Working with Custom API Path](/git-integration-for-jira-data-center/Working-with-Custom-API-Path-gij-self-managed)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

[Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

[Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/Require-Personal-Access-Tokens-for-user-actions-(create-branch-pull-request)-gij-self-managed)

**Ways to Index Git Data to Jira Issues** (this page)

[Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/Proxy-settings-on-adding-integrations-(except-AWS-CodeCommit)-gij-self-managed)

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

