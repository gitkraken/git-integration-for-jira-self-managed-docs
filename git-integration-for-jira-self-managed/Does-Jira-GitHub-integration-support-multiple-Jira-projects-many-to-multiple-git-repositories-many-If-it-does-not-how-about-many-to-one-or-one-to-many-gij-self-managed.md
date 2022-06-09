---

title: Does Jira+GitHub integration support multiple Jira projects (many) to multiple git repositories (many)? If it does not, how about many-to-one or one-to-many?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Yes — it does support repositories supporting many projects.  That said, the associations are made by the developers when they commit code to a specific issue key (which is part of a project). The permission that allows a user to see these commits in a Jira project is whether they have the "**View Development Tools**" permission for that project (that's a Jira setting).

The only project permissions that the Git Integration for Jira app has are for the Repository Browser (Git dropdown menu). To associate a repository with all Jira projects or only specific projects, see [Project permissions setting](/git-integration-for-jira-self-managed/using-the-connect-repository-wizard-gij-self-managed##Settings) in the Connect to Git Repository wizard or [associating project permissions](/git-integration-for-jira-self-managed/associating-project-permissions-gij-self-managed) via Edit repository settings in the Git Repositories configuration page.

