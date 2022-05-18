---

title: Email Support
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
If you need help with the Git Integration for Jira app, please e-mail us: [support@bigbrassband.com](mailto:support@bigbrassband.com).

Please include the "Support Zip" that Jira produces for diagnosing issues.

Also include information about:

*   How long have you been experiencing this problem?

*   If there were any changes to the environment that would be notable?


You can produce the "Support Zip" by following the steps in [this article](/wiki/spaces/GIJDC/pages/2039447557) or by accessing `http://[JiraServerNameHere]/plugins/servlet/troubleshooting/view/`.

**Note**
Jira Cloud does not have the Support Zip feature.

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/thbjckk3kv) _to open this video in a new browser tab for more viewing options._

Export Jira Support Zip settings to get the best support.

If the support zip is larger than 15 MB _(too large for our support system to receive by email) -_ contact us: [support@bigbrassband.com](mailto:support@bigbrassband.com) and we will provide a secure location to upload the support zip.

## Memory warnings before GC

NEW! VERSION 4.0

This type of information can be obtained from the logs.

The memory warnings are added to the logs before GC tasks. This provides admins a window for monitoring memory issues. The following data is logged if the threshold is met:

*   amount of free memory in the Java Virtual Machine in bytes;

*   summary size of index files in bytes (for cloned repositories).


Administrators can view these logs and do maintenance routines if needed. You may send the logs to our support email for further analysis.

**Log settings**
In order to see the log messages, you need to be sure that the logger severity for `'com.bigbrassband.jira.git.jiraservices.jobs'` (Jira settings ➜ System) is set up on the **INFO** or lower (please check it on `http://<server>/jira/secure/admin/ViewLogging.jspa` – _Jira settings ➜ Logging and profiling_).

The Git Integration for Jira app will automatically use the WARN logger severity if the memory size tolerance has been reached. If administrators doesn't want to see such logs in all GC runs, apply the WARN severity level.

* * *

### Related articles

*   Page:

    [App Support](/git-integration-for-jira-self-managed/App-Support) (Git Integration for Jira Data Center)

*   Page:

    [Known Issues](/git-integration-for-jira-self-managed/Known-Issues) (Git Integration for Jira Data Center)

*   Page:

    [Scheduling Jobs](/git-integration-for-jira-self-managed/Scheduling-Jobs) (Git Integration for Jira Data Center)

*   Page:

    [Recommended Jira memory settings](/wiki/spaces/GIJDC/pages/873332818/Recommended+Jira+memory+settings) (Git Integration for Jira Data Center)

*   Page:

    [General Settings](/git-integration-for-jira-self-managed/General-Settings) (Git Integration for Jira Data Center)

*   Page:

    [Plugin Data Storage](/wiki/spaces/GIJDC/pages/1598193683/Plugin+Data+Storage) (Git Integration for Jira Data Center)