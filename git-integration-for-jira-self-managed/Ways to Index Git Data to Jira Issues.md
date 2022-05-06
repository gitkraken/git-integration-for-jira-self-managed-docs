---

title: Ways to Index Git Data to Jira Issues
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Ways to Index Git Data to Jira Issues

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1207828916/Ways+to+Index+Git+Data+to+Jira+Issues>

* * *

There are several ways to associate git data to Jira issues:

|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| **Objective** | **Method/Trigger** | **Description** | **Example** | **Video** |
| Link commit to Jira issue | Commit message | Commit by a Jira key in the commit message. | "ABC-123 add fix for bug" | [vid link](https://fast.wistia.net/embed/iframe/7kj43knu4m) |
| Link commit to Jira issue | Git note | Commit by a Jira key in git notes to the commit. | \-  | \-  |
| Associate commit to Jira issue | Change commit issues\` in the \`Commits\` tab of a repository in the Repository Browser | Associate git commit(s) to Jira issue via Commits tab of a repository in the Repository Browser. | TEST-1, TEST-4 | \-  |
| Associate commit to Jira issue | Change commit issues in the View full commit dialog of the selected commit in Commits tab | Associate git commits to Jira issue via View full commit dialog in Commits tab. | TEST-1, TEST-4 | \-  |
| Link commits to Jira issue | Pull/merge request | PR/MR Jira key in the pull/merge request comment. | "Merge branch 1.5.1-a6b4c1d5e3f2 to ABC-123 when bug is fixed." | \-  |
| Link branch to Jira issue | Commit message | Adding a Jira key in the branch name. | "ABC-123-add-fix-for-bug" | \-  |
| Link branch to Jira issue | Associated git commits | The branch commit is already associated to the Jira issue. | "ABC-123-add-fix-for-bug" | \-  |
| Link pull/merge request to a Jira issue | Pull Request | Merge/Pull request by a Jira key in the MRs/PRs name. | "ABC-123 merge branch add fix for bug" | \-  |
| Link pull/merge request to a Jira issue | Add a description to a PR/MR after creation via the git service web portal | Merge/Pull request by a Jira key in the MRs/PRs description in the git service web portal | "This branch from this pull/merge request will be merged to ABC-123" | \-  |
| Link pull/merge request to Jira issue | Associated git commits | Merge/Pull request if the MR/PR commits are already associated. | A commit in the PR/MR is already linked to ABC-123 | \-  |
| Link pull/merge request to Jira issue | Associated git commits | Merge/Pull request by a Jira key in the MRs/PRs base or compare branch. | \-  | \-  |
| Tag a commit | Associated tags in a Jira issue. (See example) | Associated tags in a Jira issue.  <br>Tags are associated only with a Jira issue by Jira keys that are specified in commits that belong to the tag.<br><br>**Note:** Specifying a Jira key in the name of a tag does NOT associate this tag with the mentioned Jira issue. | $ git tag -a v3.7 9f1a4c2 | \-  |

## Manually associate git commits to Jira issues

For more information on this topic, see documentation [Associate git commit to Jira issues manually](https://bigbrassband.com/git-integration-for-jira/documentation/linking-git-commits-to-jira-issues.html#bbb-nav-manually-link-git-commits-to-jira-issues).

## More how-to articles

*   Page:
    
    [Creating Personal Access Tokens](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens)
    
*   Page:
    
    [Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters)
    
*   Page:
    
    [Working with Custom API Path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path)
    
*   Page:
    
    [Creating and configuring SSH keys (Windows/MacOS/Linux)](/wiki/spaces/GIJDC/pages/183271450)
    
*   Page:
    
    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849)
    
*   Page:
    
    [Setting Project Permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions)
    
*   Page:
    
    [How to get a quote?](/wiki/spaces/GIJDC/pages/1165721603)
    
*   Page:
    
    [Ways to Index Git Data to Jira Issues](/wiki/spaces/GIJDC/pages/1207828916/Ways+to+Index+Git+Data+to+Jira+Issues)
    
*   Page:
    
    [Proxy settings on adding integrations (except AWS CodeCommit)](/wiki/spaces/GIJDC/pages/1808007195)
    
*   Page:
    
    [Configure Source Code Diff Viewing](/wiki/spaces/GIJDC/pages/2054881287/Configure+Source+Code+Diff+Viewing)