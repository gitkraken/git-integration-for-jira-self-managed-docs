---

title: Nested repository
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

A nested repository is a Git repository that exists inside the working directory of another Git repository. In other words, it’s a repository within a repository. Each nested repository functions independently, with its own commit history, branches, and remote configurations.

&nbsp;

## Permissions

### GitHub

To use GitHub submodules, you need at least read access to the "Contents" and "Metadata" of the repository itself, as well as any submodule repositories. This ensures that you can clone and update the submodules properly.

### GitLab

Managing permissions for nested repositories (projects within groups and subgroups) involves assigning roles to users or groups, which determine their access levels. For this case, the minimum role is Reporter – which can view code and issues, but cannot create or edit them.

### Azure DevOps

To access Git submodules in Azure DevOps, the minimum permissions required are for the build service account to have access to both the main repository and the submodule repository. If the "Protect access to repositories in YAML pipelines" setting is enabled, you may need to explicitly reference the submodule in your pipeline to avoid permission errors.

### Bitbucket

To access a Bitbucket submodule, the minimum permissions required are read access to the submodule repository for the user or SSH key being used. Ensure that the user has the appropriate permissions set in Bitbucket for both the parent and submodule repositories.

### AWS CodeCommit

To work with AWS submodules, you need to ensure that the IAM user or role has the necessary permissions to access the repositories and perform actions like cloning and updating submodules. This typically includes permissions for Git operations and access to the specific resources involved in your project.

&nbsp;

## How nested repositories work

When a Git repository is placed inside another repository’s directory, it does not automatically become part of the parent repository. The parent repository does not track the nested repo’s files unless they are plainly added, which can sometimes cause confusion in version control workflows.

&nbsp;

## Practical use for developers

Nested repositories can be useful in some specific development scenarios:

-   **Develop modular projects**

    Developers working on large projects can organize their code into separate repositories while still keeping them inside a main project folder.

-   **Manage third-party dependencies**

    Developers can include third-party projects or libraries as nested repositories rather than manually copying their source code. This helps in maintaining dependencies up to date by pulling changes from the remote repository when needed.

-   **Standalone version control**

    Each nested repository keeps its own history and branches. This will allow teams to work on different components independently. This is useful in cases where sub-teams or external collaborators need full control over a specific module.

-   **Custom development environments**

    Some teams maintain separate repositories for configuration files, infrastructure scripts, or experimental features inside their main project repository. This allows for quick testing and switching between configurations without affecting the core project.

&nbsp;

## Some challenges with using nested repositories

While nested repositories offer some benefits, they also come with challenges. For instance:

-   **Files are not tracked**

    The parent repository does not automatically track the nested repository’s files unless they are manually added.

-   **Conflicts on merging can occur**

    If multiple developers work on both the parent and nested repositories, conflicts can arise when merging changes.

-   **Requires extra steps on deploying projects**

    Deploying projects with nested repositories may require extra steps to ensure all repositories sync correctly.

&nbsp;

## Nested repository as a formal feature

Various Git hosting services and platforms implement distinct policies for managing nested repositories. Although Git does not natively support "nested repositories" as a formal feature, certain services offer equivalent functionality under different name or terms.

For example:

-   **GitHub:** Supports submodules with .gitmodules file tracking.

-   **GitLab:** Provides UI support for managing submodules.

-   **Bitbucket:** Supports submodules with limited UI visibility.

-   **Azure DevOps:** Allows working with submodules inside projects.


&nbsp;
* * *

[**Prev:** Using the Connect Repository wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed)

[**Next:** Adding and connecting a nested repository](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed)

