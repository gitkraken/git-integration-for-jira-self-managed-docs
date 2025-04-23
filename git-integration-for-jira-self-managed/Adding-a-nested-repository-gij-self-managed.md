---

title: Adding a nested repository
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

## Example: Adding a nested repository with Git Submodule

While, GitHub does not allow nested repositories (Git doesn't allow this for bare repositories), you can use submodules to nest repositories on the "client side" in the working tree:

1.  Clone the parent directory.

2.  Add the sub-repository as a [submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules):

    `git submodule add https://github.com/\<username\>/\<sub_repo\>.git`

    The `\<sub_repo\>` module will then be linked to the parent repo and can be found in the `\<sub_repo\>` directory.

3.  Commit (`.gitmodules` and `\<sub_repo\>`), push and you're done.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <code>git submodule add</code> command works on most Git services that supports it. Check with your Git service documentation on how to add a submodule.
    </div>
    </div>
</div>

&nbsp;

## Adding a nested repository with Git Integration for Jira app

Adding a nested repository configuration through the Git Integration for Jira app is similar to adding a plain Git repository.

1.  Go to the Manage integration configuration page.

    ![](/wp-content-uploads/)

2.  Click either the Connect to Git repository button or the Git icon on the integration panel.

3.  On the following screen, paste the clone URL of the submodule from your git service portal.

4.  On the following screen, the input fields depends on what type of clone URL you’ll be using:

    *   **HTTPS authentication** – Enter your credentials such as username and password. For the password, provide the PAT as the password.

    *   **SSH authentication** – Provide the private ssh key. Enter the passphrase if your SSH key requires a passphrase.

5.  On the Settings screen, leave all options as is. Click Finish to complete this setup.

The nested repository configuration is added to the Manage integrations list.

&nbsp;
* * *

[**Prev:** Edit repository settings](/git-integration-for-jira-data-center/edit-repository-settings-gij-self-managed)

[**Next:** SSL verify](/git-integration-for-jira-data-center/ssl-verify-gij-self-managed)


