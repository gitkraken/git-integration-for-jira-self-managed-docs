---

title: What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


The commit retains the association even in the new project. The Git Integration for Jira app supports history tracking. Thus, when moving a ticket to a new project whose issue key has changed, the association will still work.

The steps below provides an outline that you can follow to verify that the issue associations with commits are retained:

1.  Associate a commit with issue (ex. **TEST-1**)
    
2.  Move the issue **TEST-1** to a new project (ex. **PM**)
    
3.  New issue key for **TEST-1** is **PM-18**
    
4.  Check that original commit in **TEST-1** is still available in **PM-18**.  The commit should be there (Git Commits tab).
    
5.  In the **Git Repositories** configuration page, perform **Reset** and **Reindex** (under ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions) on the selected repository to make sure that the commits are in the correct location.
    

The Git Integration for Jira app also supports multiple issue keys in a commit message.

