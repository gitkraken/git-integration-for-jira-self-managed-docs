---

title: How do I completely rebuild plugin indexes?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
If you think that the Git indexes are corrupt and needed to be completely rebuilt, please do the following:

1.  Disable the Git Integration for Jira app (![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Jira administration_ ➜ _Manage apps_).

2.  Remove the following folders:

    `{JIRA_HOME}/cache/indexes/plugins/jira-git-files`
    `{JIRA_HOME}/cache/indexes/plugins/jira-git-revisions`

3.  Enable Git Integration for Jira app. 


On the next startup, the app will create the above folders again.

If you have large Git repositories, please do this after prime time.

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