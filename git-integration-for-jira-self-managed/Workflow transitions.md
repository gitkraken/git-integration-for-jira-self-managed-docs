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

[« Advanced examples](/git-integration-for-jira-self-managed/Advanced-examples)

[Viewing workflows »](/git-integration-for-jira-self-managed/Viewing-workflows)

### More related topics about smart commits

*   Page:

    [Smart commits](/git-integration-for-jira-self-managed/Smart-commits) (Git Integration for Jira Data Center)

*   Page:

    [Basic commands](/git-integration-for-jira-self-managed/Basic-commands) (Git Integration for Jira Data Center)

*   Page:

    [Workflow transitions](/git-integration-for-jira-self-managed/Workflow-transitions) (Git Integration for Jira Data Center)

*   Page:

    [Advanced examples](/git-integration-for-jira-self-managed/Advanced-examples) (Git Integration for Jira Data Center)

*   Page:

    [Viewing workflows](/git-integration-for-jira-self-managed/Viewing-workflows) (Git Integration for Jira Data Center)

*   Page:

    [Smart commits helper](/wiki/spaces/GIJDC/pages/1930398529/Smart+commits+helper) (Git Integration for Jira Data Center)

*   Page:

    [Smart commits General setting](/wiki/spaces/GIJDC/pages/1930398554/Smart+commits+General+setting) (Git Integration for Jira Data Center)

*   Page:

    [Scripting (Jira git workflow hooks)](/wiki/spaces/GIJDC/pages/1930398579) (Git Integration for Jira Data Center)