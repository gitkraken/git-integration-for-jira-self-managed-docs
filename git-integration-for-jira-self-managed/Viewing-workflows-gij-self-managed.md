---

title: Smart commits - Viewing workflows
description: "Find the transition names to use in smart commits by viewing an issue's workflow, and learn how names are shortened and kept unique."
product: Git Integration for Jira Data Center
feature: Smart Commits
content_type: how-to
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [workflows, transitions, transition names, view workflow, smart commits]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Smart commits – Viewing workflows"
    nav_order: 40
    nav_parent: "smart-commits-gij-self-managed"
    page_type: "content"
    card_icon: "git-commit"
    card_color: "blue"
    card_description: "Find the transition names to use in smart commits by viewing an issue's workflow, and learn how names are shortened and kept unique"
---

> **Warning:** Accessing the View workflow feature on the Issue page requires a user or user group to have the <b>View Read-Only Workflow</b> project permissions.


![](/wp-content/uploads/gij-gitserver-issue-page-view-workflow-sel.png)

You can see the available custom workflow transition commands for use with smart commits by doing the following:

1.  Open an issue and click **View Workflow** from the context of the issue (near the issue’s **Status**).

2.  Hover a status.

    When you hover a status – it will highlight available transitions. This is the transition name that is used in smart commits and not the status name.

    ![](/wp-content/uploads/gij-jira-workflow-hover-c.png)

Below is an example using the above workflow where the issue is in OPEN status and want to send it to BUSINESS SPEC status:

**<ISSUE\_KEY>** **#to-business-spec** or,<br>
**<ISSUE\_KEY>** **#to-business** _and even_,<br>
**<ISSUE\_KEY>** **#to** _(yes, this works, as long as it does not conflict with another transition name)_

Do note that invalid characters can be used in the transition name. Jira accepts most of them and they can be used. However, smart commits will only process letters and dash characters.

Thus, the part of the transition name up to the invalid character can be used for transitions; where spaces become "-".

&nbsp;

#### Example 1:

| Transition name | Smart Commit transition |
|:----------------|:------------------------|
| `SEND_TO_QA`    | **SEND**                |
| `SEND-TO_QA`    | **SEND-TO**             |
| `SEND TO_QA`    | **SEND-TO**             |

There must be at least one unique way to call each transition name. If you have multiple transition names from a single status that use the same word, the smart commits will fail.

&nbsp;

#### Example 2:

Another example, where an issue status NEW has these two transition paths:

*   `SEND_TO_DEVELOPMENT`
*   `SEND_TO_BACKLOG`
    
The invalid characters are used before unique transition names are possible. Both will become "**#SEND**". Therefore, they are not unique and these transitions will fail.

&nbsp;

#### Example 3:

Finally, the transition names have spaces instead:

*  `SEND TO DEVELOPMENT`
*  `SEND TO BACKLOG`

Both of these transitions are smart commit-friendly and the possible transitions are:

*   `#SEND-TO-D...`
*   `#SEND-TO-B...`

The "..." indicates the truncation with the least character length to have the transition names be recognized as unique by Smart Commits. Any length shorter than this will fail the transition as explained in [**Example 2**](#example-2) above.

> **Info:** If a smart commit fails, an email notification is sent to either the Jira user, or to the Git user if a Jira user can't be identified.

&nbsp;
* * *

[**Prev:** Workflow transitions](/git-integration-for-jira-data-center/workflow-transitions-gij-self-managed)

[**Next:** Smart commits helper](/git-integration-for-jira-data-center/smart-commits-helper-gij-self-managed)


