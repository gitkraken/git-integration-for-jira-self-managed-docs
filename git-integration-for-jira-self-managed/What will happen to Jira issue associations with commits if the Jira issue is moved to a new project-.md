---

title: What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2051014669>

* * *

The commit retains the association even in the new project. The Git Integration for Jira app supports history tracking. Thus, when moving a ticket to a new project whose issue key has changed, the association will still work.

The steps below provides an outline that you can follow to verify that the issue associations with commits are retained:

1.  Associate a commit with issue (ex. **TEST-1**)
    
2.  Move the issue **TEST-1** to a new project (ex. **PM**)
    
3.  New issue key for **TEST-1** is **PM-18**
    
4.  Check that original commit in **TEST-1** is still available in **PM-18**.  The commit should be there (Git Commits tab).
    
5.  In the **Git Repositories** configuration page, perform **Reset** and **Reindex** (under ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions) on the selected repository to make sure that the commits are in the correct location.
    

The Git Integration for Jira app also supports multiple issue keys in a commit message.

*   Page:
    
    [How do Git commits get associated with a Jira issue?](/wiki/spaces/GIJDC/pages/2051571713)
    
*   Page:
    
    [How do I ensure people are following our organization's process for source code?](/wiki/spaces/GIJDC/pages/2051768321)
    
*   Page:
    
    [What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?](/wiki/spaces/GIJDC/pages/2051014669)
    
*   Page:
    
    [What are developer licenses?](/wiki/spaces/GIJDC/pages/2051964929)
    
*   Page:
    
    [How to associate a commit, branch or pull request AFTER it has been created?](/wiki/spaces/GIJDC/pages/2062974977)