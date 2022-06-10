---

title: How do I let people browse Git securely but without defining Git IDs for everyone?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
With the Git Integration for Jira app, you only need to define a single ID for the Jira server.  Jira then lets authorized Jira users browse Git.

You can restrict access to the Repository Browser _(views git list/repo folders in Jira)_ for the selected repository by associating the project permissions. On Jira, the **View Development Tools** permission must be granted to Users / Group / Project Roles.

Configure this setting via:

*   Jira dashboard menu:

    *   Git ➜ **Manage repositories**

    *   Actions ➜ Edit integration/repository settings ➜ **Project Permissions**

    *   Unmark the _**All Projects**_ checkbox and set one or two projects.

*   Connect Wizard:

    *   On the Integration Settings screen ➜ **Project Permissions**.

    *   Unmark the _**All Projects**_ checkbox and set one or two projects.


