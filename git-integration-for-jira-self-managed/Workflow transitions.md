---

title: Workflow transitions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The simple Jira workflow does not contain explicit transition names. These kind of workflow with no explicit transition names are becoming more popular as Atlassian is suggesting them to administrators upon project creation.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398464/jira-simple-workflow.png?version=1&modificationDate=1630642890131&cacheVersion=1&api=v2&width=217&height=232)

The name of the status is the transition. So, using the basic example above, the valid transitions from DONE are:

*   **#to-do**

*   **#in-progress**

*   **#in-review**


**Transition names**
The workflow transition names must be unique.

**Absence of transition names**
When there are no transition names — just use the status names. If there is a space, replace it with "–" (hyphens). For example, `CODE REVIEW` becomes `#code-review`.

**Commit authors**
Only letters and "-" (dash) are valid for workflow transition names for smart commits. Any other characters are treated as invalid. Smart commits will ONLY use the valid characters before the occurrence of an invalid character for processing.

**Jira Administrators**
When adding transitions in the Workflow editor, make transition names simple and easy to remember. Only use letters and only one space between words.

[« Advanced examples](/wiki/spaces/GIJDC/pages/1930398446/Advanced+examples)

[Viewing workflows »](/wiki/spaces/GIJDC/pages/1930398494/Viewing+workflows)

### More related topics about smart commits

*   Page:

    [Smart commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits) (Git Integration for Jira Data Center)

*   Page:

    [Basic commands](/wiki/spaces/GIJDC/pages/1930398422/Basic+commands) (Git Integration for Jira Data Center)

*   Page:

    [Workflow transitions](/wiki/spaces/GIJDC/pages/1930398464/Workflow+transitions) (Git Integration for Jira Data Center)

*   Page:

    [Advanced examples](/wiki/spaces/GIJDC/pages/1930398446/Advanced+examples) (Git Integration for Jira Data Center)

*   Page:

    [Viewing workflows](/wiki/spaces/GIJDC/pages/1930398494/Viewing+workflows) (Git Integration for Jira Data Center)

*   Page:

    [Smart commits helper](/wiki/spaces/GIJDC/pages/1930398529/Smart+commits+helper) (Git Integration for Jira Data Center)

*   Page:

    [Smart commits General setting](/wiki/spaces/GIJDC/pages/1930398554/Smart+commits+General+setting) (Git Integration for Jira Data Center)

*   Page:

    [Scripting (Jira git workflow hooks)](/wiki/spaces/GIJDC/pages/1930398579) (Git Integration for Jira Data Center)