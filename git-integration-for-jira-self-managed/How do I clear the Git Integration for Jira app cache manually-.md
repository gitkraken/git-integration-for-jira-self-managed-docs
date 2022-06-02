---

title: How do I clear the Git Integration for Jira app cache manually?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
If you think that the Git caches are corrupt and needed to be removed, please do the following:

1.  Disable the Git Integration for Jira app (![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Jira administration_ ➜ _Manage apps_).

2.  Go to `<jira_home>`.

3.  Delete the index:

    **Example:** `rm -rf <jira_home>/caches/indexes/plugins/jira-git-*`

4.  Delete the cache:

    **Example:** `rm <jira_home>/data/git-plugin/indexed-revisions-info-cache`

5.  Enable the Git Integration for Jira app.

6.  Reindex all integration repositories by performing the next two steps.

7.  Go to ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Jira administration** ➜ **Applications**. On the sidebar under _Git Integration for Jira_, click **Git Repositories**.

8.  Click **Reindex All**.


**The above solution also applies to:**
Commit information that are not shown for commits having issue key(s) in its message that were already indexed 
