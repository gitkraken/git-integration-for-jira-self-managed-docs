---

title: How do I enable debug logging level for Git Integration for Jira app?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The debug logging level can be set by performing the following steps:

1.  On your Jira dashboard, go to ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Jira Administration** ➜ **System**.

2.  On the sidebar, under **System support**, select **Logging and profiling**.

3.  Scroll down to the _**Default Loggers**_ section, then click **Configure**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2038792196/gitserver-jira-admin-system-default-loggers-dlg(c).png?version=1&modificationDate=1640073725401&cacheVersion=1&api=v2&width=544&height=173)
4.  On the following screen, enter `com.bigbrassband.jira.git` for _**Package name**_ then set _**Logging Level**_ to **DEBUG**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2038792196/gitserver-jira-admin-system-def-logs-cfg-dlg(c).png?version=1&modificationDate=1640073845525&cacheVersion=1&api=v2&width=544&height=275)
5.  Click **Add** to add this configuration to the _Debug Loggers_ list.



To report errors:

1.  Collect errors and send log file to [support@bigbrassband.com](mailto:support@bigbrassband.com).

2.  Also, please add your Jira version, Git plugin version and OS used to run Jira.


The Git Integration for Jira app — like most Atlassian Marketplace apps — writes to the standard Jira log. The setting you've enabled here causes it to write more log data.
