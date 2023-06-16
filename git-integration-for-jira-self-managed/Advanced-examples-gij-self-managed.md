---

title: Smart commits - Advanced examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- smart commits advanced examples -->

### A single action on a single issue

**TEST-100** **#time** 2w 1d 4h 30m _This is a time log comment_

Records the specified worklog `#time` of **2 weeks, 1 day, 4 hours and 30 minutes** and adds worklog comment "_This is a time log comment_" to the issue, TEST-100.

* * *

### Multiple actions on a single issue

**TEST-100** **#time** 4h 30m _Fix null pointers_ **#comment** _Fixed code_ **#resolve**

Logs specified `#time` of **4 hours and 30 minutes** and add worklog comment "_Fixed null pointers_" to the issue, TEST-100; adds the `#comment` "Fixed code" and resolves the issue.

* * *

### A single action on multiple issues

**TEST-100 TEST-101 TEST-102** **#resolve**

Resolves specified issues.

* * *

### Multiple actions on multiple issues

**TEST-100 TEST-101 TEST-102** **#resolve** **#time** 2d 4h **#comment** _Fixed code_

Resolves specified issues; logs specified `#time` of **2 days and 4 hours** and adds `#comment` "Fixed code" against the issues.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Support is already implemented for multi-line commit messages with smart commits.
    </div>
    </div>
</div>

* * *

### Multi-line examples

The following examples show correct usage of the smart commit message (multi-line):

```bash
TST-1 implemented feature 1
TST-1 \#comment some comment
in Jira
on several lines
TST-1 \#resolve
TST-2 \#time 1h 30m
```

_In this example, an issue key that is present on every line is a valid multi-line commit message._

* * *

```bash
TST-1 implemented feature 1
\#comment some comment
in Jira on several lines
\#resolve TST-2
\#time 1h 30m
```

_This is the equivalent smart commit message based from the above example._

* * *

```bash
TEST-3 Background color of settings should be lighter
TEST-3 \#in-progress \#time 1h
TEST-4 resolve TEST-2 \#resolve
```

_This example, containing several issue keys, is also a valid multi-line smart commit message._

&nbsp;
* * *

[**Prev:** Smart commit - Basic commands](/git-integration-for-jira-data-center/)

[**Next:** Workflow transitions](/git-integration-for-jira-data-center/workflow-transitions-gij-self-managed)


