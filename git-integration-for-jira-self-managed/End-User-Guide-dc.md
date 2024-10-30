---

title: End User Guide - GIJ DC
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Introduction to GIJ
Thank you for using Git Integration for Jira! First, let’s go over how information will be displayed in jira through our application.

## Jira Issue View

GIJ will display commits, branches, and pull/merge requests associated with a specific Jira issue. The Jira issue keys must be included in the commit message, the branch name, and the pull/merge request title in order for GIJ to link the item to the respective Jira issue.

![Jira Issue View](/wp-content/uploads/Jira-dc-Issue-Breakdown.png)
Breakdown of information provided by GIJ in Jira issues:
### Git Commits Tab
1. Git Commits tab in the activity stream, broken down by repository
2. Individual commit, noted by developer that made the commit
3. Commit message
4. Commit line change summary by file
5. Link to view Code diff in Jira
### Git Integration Panel
6. Commit count
7. Option to Create a branch directly from a Jira Issue. Associated Branches with change comparison count to main repository branch.
8. Option to Create a pull/merge request directly from a Jira issue. Associated pull/merge Requests with status

Additionally, the [Git Rollup tab](https://help.gitkraken.com/git-integration-for-jira-data-center/git-roll-up-tab-docs-gij-self-managed/) allows you to see a summary of the files, lines and the developers who have made the changes associated with the Jira issue.
![Git Rollup Tab](/wp-content/uploads/gij-jira-issue-git-rollup-summary.png)

## Linking Behavior

GIJ uses the Jira issue key to determine whether or not a repository activity(commits, branches, pull/merge Requests) is linked to any Jira items. In order for the linking to occur, you need to include the Jira issue key in the commit Message, the branch name, and the pull request title. It does not need to be in any specific part of the message or name as long as it is included.Please see: [Linking Git Commits to Jira Issues](https://help.gitkraken.com/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed/) for more details.

![Jira Issue Key](/wp-content/uploads/Jira-Issue-key-linking-dc.png)

![Commit Example](/wp-content/uploads/Linking-Commit-example.png)

![Pull request Example](/wp-content/uploads/Pull-Request-Linking-Example.png)

## Creating Branches
You can [create branches](https://help.gitkraken.com/git-integration-for-jira-cloud/create-branch-gij-cloud/) directly from a Jira issue using GIJ. To do this, first open the ‘Git Integration’ panel from the right hand side of the Jira issue, then click the ‘Create branch’ option.

![Create Branch 1](/wp-content/uploads/Enduserguide-Cloud-Create-Branch-1dc.png)

Select the desired Repository to create the branch in, the source branch, and the branch name. Make sure that the Jira Issue key is included in the branch name.

![Create Branch 2](/wp-content/uploads/Enduserguide-Cloud-Create-Branch-2-dc.png)

You will see a pop up after the branch is created, and you will be able to link our directly to the newly created branch.

## Creating Pull/Merge Requests
You can [create Pull/Merge Requests](https://help.gitkraken.com/git-integration-for-jira-cloud/create-pull-or-merge-request-gij-cloud/) directly from Jira using GIJ as well. To do this, first open the ‘Git Integration’ panel from the right hand side of the Jira issue, then click the ‘Create Pull Request/Merge Request’ option.

![Create PR 1](/wp-content/uploads/Enduserguide-Cloud-Creating-PR-1-dc.png)
Select the repository, source and target branches, and make sure that the title of the pull request contains the Jira Issue key, and click the ‘Create pull/merge request’ button.

![Create PR 2](/wp-content/uploads/Enduserguide-Cloud-Creating-PR-2-dc.png)
You will see a pop up after the branch is created, and you will be able to link our directly to the newly created branch.


## Personal Access Tokens
You can manage the Personal Access Tokens that will be used to authenticate your requests to create branches and pull Requests directly from your Jira Profile. You will need to provide a token for each integration.Please see [Creating Personal Access Tokens]https://help.gitkraken.com/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed/) for detailed instructions for creating your PAT.

To manage your PAT’s, click your profile picture, and choose ‘Profile’



![PAT](/wp-content/uploads/Jira-Profile-1-dc.png)

![PAT](/wp-content/uploads/Jira-Profile-2-dc.png)

