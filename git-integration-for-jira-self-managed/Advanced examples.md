---

title: Advanced examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
|     |
| --- |
| **Usage and Description** |
| A single action on a single issue.<br><br>**Example:** |
| **TEST-100** **#time** 2w 1d 4h 30m This is a time log comment |
| Records the specified worklog `#time` of **2 weeks, 1 day, 4 hours and 30 minutes** and adds worklog comment "_This is a time log comment_" to the issue, TEST-100. |

|     |
| --- |
| Multiple actions on a single issue.<br><br>**Example:** |
| **TEST-100** **#time** 4h 30m Fix null pointers **#comment** Fixed code **#resolve** |
| Logs specified `#time` of **4 hours and 30 minutes** and add worklog comment "_Fixed null pointers_" to the issue, TEST-100; adds the `#comment` "Fixed code" and resolves the issue. |

|     |
| --- |
| A single action on multiple issues.<br><br>**Example:** |
| **TEST-100 TEST-101 TEST-102** **#resolve** |
| Resolves specified issues. |

|     |
| --- |
| Multiple actions on multiple issues.<br><br>**Example:** |
| **TEST-100 TEST-101 TEST-102** **#resolve** **#time** 2d 4h **#comment** Fixed code |
| Resolves specified issues; logs specified `#time` of **2 days and 4 hours** and adds `#comment` "Fixed code" against the issues. |

VERSION 2.6.33+
Implemented support for multi-line commit messages with smart commits.

#### multi-line

The following examples show correct usage of the smart commit message (multi-line):

|     |
| --- |
| **TST-1** implemented feature 1  <br>**TST-1** **#comment** some comment  <br>in Jira  <br>on several lines  <br>**TST-1** **#resolve**  <br>**TST-2** **#time** 1h 30m |
| _In this example, an issue key that is present on every line is a valid multi-line commit message._ |

|     |
| --- |
| **TST-1** implemented feature 1  <br>**#comment** some comment  <br>in Jira on several lines  <br>**#resolve** TST-2  <br>**#time** 1h 30m |
| _This is the equivalent smart commit message based from the above example._ |

|     |
| --- |
| **TEST-3** Background color of settings should be lighter  <br>**TEST-3** **#in-progress** **#time** 1h  <br>**TEST-4** resolve **TEST-2** **#resolve** |
| _This example, containing several issue keys, is also a valid multi-line smart commit message._ |
