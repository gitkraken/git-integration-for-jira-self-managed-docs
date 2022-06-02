---

title: How do I completely rebuild plugin indexes?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
If you think that the Git indexes are corrupt and needed to be completely rebuilt, please do the following:

1.  Disable the Git Integration for Jira app (![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Jira administration_ ➜ _Manage apps_).

2.  Remove the following folders:

    `{JIRA_HOME}/cache/indexes/plugins/jira-git-files`
    `{JIRA_HOME}/cache/indexes/plugins/jira-git-revisions`

3.  Enable Git Integration for Jira app. 


On the next startup, the app will create the above folders again.

If you have large Git repositories, please do this after prime time.

