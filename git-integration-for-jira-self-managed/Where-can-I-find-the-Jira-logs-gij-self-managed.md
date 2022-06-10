---

title: Where can I find the Jira logs?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Git logging is also found in the standard Jira logs. This can change based on how Jira was installed, which version you have, and which version you started with. Generally, start by looking at `catalina.out` in the Jira Tomcat directory.

If you need to troubleshoot the installation of the Git Integration for Jira app (_or any Jira issue_), the best place to turn to or check is the logs that Jira offers.

Please follow the directions from Atlassian: [Atlassian Logging and Profiling](https://confluence.atlassian.com/display/Jira/Logging+and+Profiling) and send us the following file:

`atlassian-jira.log` (if Windows)

`catalina.out` (if Linux)
