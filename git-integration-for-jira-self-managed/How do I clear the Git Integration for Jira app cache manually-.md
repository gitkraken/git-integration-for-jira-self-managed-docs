---

title: How do I clear the Git Integration for Jira app cache manually?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# How do I clear the Git Integration for Jira app cache manually?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2053406737>

* * *

If you think that the Git caches are corrupt and needed to be removed, please do the following:

1.  Disable the Git Integration for Jira app (![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Jira administration_ ➜ _Manage apps_).
    
2.  Go to `<jira_home>`.
    
3.  Delete the index:
    
    **Example:** `rm -rf <jira_home>/caches/indexes/plugins/jira-git-*`
    
4.  Delete the cache:
    
    **Example:** `rm <jira_home>/data/git-plugin/indexed-revisions-info-cache`
    
5.  Enable the Git Integration for Jira app.
    
6.  Reindex all integration repositories by performing the next two steps.
    
7.  Go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Jira administration** ➜ **Applications**. On the sidebar under _Git Integration for Jira_, click **Git Repositories**.
    
8.  Click **Reindex All**.
    

**The above solution also applies to:**  
Commit information that are not shown for commits having issue key(s) in its message that were already indexed 

*   Page:
    
    [What does re-index do?](/wiki/spaces/GIJDC/pages/2054291457)
    
*   Page:
    
    [Is there any way to control the reindex?](/wiki/spaces/GIJDC/pages/2053275662)
    
*   Page:
    
    [Commits are not showing right away. Can they show up faster?](/wiki/spaces/GIJDC/pages/2053570566)
    
*   Page:
    
    [How do I completely rebuild plugin indexes?](/wiki/spaces/GIJDC/pages/2053734434)
    
*   Page:
    
    [How do I clear the Git Integration for Jira app cache manually?](/wiki/spaces/GIJDC/pages/2053406737)
    
*   Page:
    
    [Is it possible to track the specified branches when reindexing?](/wiki/spaces/GIJDC/pages/2053406744)
    
*   Page:
    
    [Is there a URL I can call to trigger fetch and re-index? Would be nice to add as service hook to GitHub/Gitlab.](/wiki/spaces/GIJDC/pages/2053832750)
    
*   Page:
    
    [The git notes are still not visible in Jira. What should I do?](/wiki/spaces/GIJDC/pages/2054225956)