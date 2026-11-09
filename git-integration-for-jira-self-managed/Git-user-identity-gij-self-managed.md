---

title: Git user identity
description: Configure your Git user name and email so commits display with the matching Jira user profile link and avatar in Git Integration for Jira.
product: Git Integration for Jira Data Center
feature: Git User Identity
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
tags: [git user identity, git config, commit author, email matching, jira user]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Git user identity"
    nav_order: 160
    nav_parent: "documentation-gij-self-managed"
    page_type: "content"
---

A git user can identify himself on his local computer using the following commands:

```powershell
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

Or, for specific repository:

```powershell
$ git config user.name "John Doe"
$ git config user.email johndoe@example.com
```

&nbsp;

Then every commit is supported by the configured user information.

Hosting services _(like GitHub and BitBucket, for example)_ try to match these data in commits with a particular account:

*   **If the email is unknown, it just displays the name from the commit.**
    If there is no Jira user associated with the email, the Git Integration for Jira app will use the author's name from the commit and displays this name without any associated links.

    ![](/wp-content/uploads/gij-git-user-non-matching-email.png)

*   **If an email is configured in the local repository, the account is detected and will be displayed.**
    The Git Integration for Jira app will use the email from a commit and will search for a Jira user using this email. If the Jira user is found, the associated link to his Jira profile is displayed with the accompanying Jira avatar beside the name.

    ![](/wp-content/uploads/git-user-matching-email.png)

&nbsp;
* * *

[**Prev:** Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed)

[**Next:** Jira user information card](/git-integration-for-jira-data-center/jira-user-information-card-gij-self-managed)


