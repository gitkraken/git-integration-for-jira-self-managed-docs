---

title: FAQ - Logging
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This page contains related questions about troubleshooting using Jira logs.

Use the FAQ below to find answers to common questions.  Feel free to contact our support team ([support@bigbrassband.com](mailto:support@bigbrassband.com?subject=Help%20on%20logs%20-)) if you don't see what you're looking for.

- [How to create the support zip file?](#how-to-create-the-support-zip-file)
- [How do I enable debug logging level for Git Integration for Jira app?](#how-do-i-enable-debug-logging-level-for-git-integration-for-jira-app)
- [Where can I find the Jira logs?](#where-can-i-find-the-jira-logs)

* * *

## How to create the support zip file?

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        Jira Cloud does not have the Support Zip feature.
    </div>
    </div>
</div>

_(The old video is removed. Updated Video guide coming soon)_

Jira can produce a Support Zip file for diagnosing issues. This will give our support team a better view of the issue.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/273383583/gitserver-jira-admin-system-support-tools-zip.png?version=1&modificationDate=1640072648939&cacheVersion=1&api=v2)

You can create this file by accessing the Atlassian Support Tools in your Jira:

1.  On your Jira Server dashboard, go to **Jira Administration**.

2.  Click **System**.

3.  On the left sidebar, click **Troubleshooting and support tools**.

4.  Click the **Create support zip** tab.

5.  For **Customize zip**, leave all check marked options (recommended) or check/uncheck required information to generate.
    RECOMMENDED For Jira Data Center instances, you may include **Thread dumps** for performance analysis.

6.  Click **Create zip** to start generating support data.

Locate the generated Support Zip file and send it to [support@bigbrassband.com](mailto:support@bigbrassband.com).

## How do I enable debug logging level for Git Integration for Jira app?

The debug logging level can be set by performing the following steps:

1.  On your Jira dashboard, go to Jira Administration ➜ **System**.

2.  On the sidebar, under **System support**, select **Logging and profiling**.

3.  Scroll down to the _**Default Loggers**_ section, then click **Configure**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2038792196/gitserver-jira-admin-system-default-loggers-dlg(c).png?version=1&modificationDate=1640073725401&cacheVersion=1&api=v2&width=544&height=173)

4.  On the following screen, enter `com.bigbrassband.jira.git` for _**Package name**_ then set _**Logging Level**_ to **DEBUG**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2038792196/gitserver-jira-admin-system-def-logs-cfg-dlg(c).png?version=1&modificationDate=1640073845525&cacheVersion=1&api=v2&width=544&height=275)

5.  Click **Add** to add this configuration to the _Debug Loggers_ list.

<br>

To report errors:

1.  Collect errors and send log file to [support@bigbrassband.com](mailto:support@bigbrassband.com).

2.  Also, please add your Jira version, Git plugin version and OS used to run Jira.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app — like most Atlassian Marketplace apps — writes to the standard Jira log. The setting you've enabled here causes it to write more log data.
    </div>
    </div>
</div>
<br>

## Where can I find the Jira logs?

The Git logging is also found in the standard Jira logs. This can change based on how Jira was installed, which version you have, and which version you started with. Generally, start by looking at `catalina.out` in the Jira Tomcat directory.

If you need to troubleshoot the installation of the Git Integration for Jira app (_or any Jira issue_), the best place to turn to or check is the logs that Jira offers.

Please follow the directions from Atlassian: [Atlassian Logging and Profiling](https://confluence.atlassian.com/display/Jira/Logging+and+Profiling) and send us the following file:

*   `atlassian-jira.log` (if Windows)

*   `catalina.out` (if Linux)

