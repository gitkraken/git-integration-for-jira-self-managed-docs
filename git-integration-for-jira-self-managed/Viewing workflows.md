---

title: Viewing workflows
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Accessing the View workflow feature on the Issue page requires a user or user group to have the **View Read-Only Workflow** project permissions.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930398494/gitserver-issue-page-view-workflow-sel.png?version=1&modificationDate=1630642891465&cacheVersion=1&api=v2)

You can see the available custom workflow transition commands for use with smart commits by doing the following:

1.  Open an issue and click **View Workflow** from the context of the issue (near the issue’s **Status**).

2.  Hover a status.

    When you hover a status – it will highlight available transitions. This is the transition name that is used in smart commits and not the status name.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930398494/jira-workflow-hover(c).png?version=1&modificationDate=1630642891722&cacheVersion=1&api=v2)

Below is an example using the above workflow where the issue is in OPEN status and want to send it to BUSINESS SPEC status:

**<ISSUE\_KEY>** **#to-business-spec** or,
**<ISSUE\_KEY>** **#to-business** _and even_,
**<ISSUE\_KEY>** **#to** _(yes, this works, as long as it does not conflict with another transition name)_

Do note that invalid characters can be used in the transition name. Jira accepts most of them and they can be used. However, smart commits will only process letters and dash characters.

Thus, the part of the transition name up to the invalid character can be used for transitions; where spaces become "-".

|     |     |
| --- | --- |
| **Example 1:** |     |
| **Transition name** | **Smart Commit transition** |
| `SEND_TO_QA` | **SEND** |
| `SEND-TO_QA` | **SEND-TO** |
| `SEND TO_QA` | **SEND-TO** |
| There must be at least one unique way to call each transition name. If you have multiple transition names from a single status that use the same word, the smart commits will fail. |     |

|     |
| --- |
| **Example 2:** |
| Another example, where an issue status NEW has these two transition paths:<br><br>*   `SEND_TO_DEVELOPMENT`<br>    <br>*   `SEND_TO_BACKLOG`<br>    <br><br>The invalid characters are used before unique transition names are possible. Both will become "**#SEND**". Therefore, they are not unique and these transitions will fail. |

|     |
| --- |
| **Example 3:** |
| Finally, the transition names have spaces instead:<br><br>*   `SEND TO DEVELOPMENT`<br>    <br>*   `SEND TO BACKLOG`<br>    <br><br>Both of these transitions are smart commit-friendly and the possible transitions are:<br><br>*   **#SEND-TO-D...**<br>    <br>*   **#SEND-TO-B...**<br>    <br><br>The "..." indicates the truncation with the least character length to have the transition names be recognized as unique by Smart Commits. Any length shorter than this will fail the transition as explained in **Example 2** above. |

If a smart commit fails, an email notification is sent to either the Jira user, or to the Git user if a Jira user can't be identified.

[« Workflow transitions](/git-integration-for-jira-self-managed/Workflow-transitions)

[Smart commits helper »](/wiki/spaces/GIJDC/pages/1930398529/Smart+commits+helper)

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