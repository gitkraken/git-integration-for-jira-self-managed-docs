---

title: Adding and connecting a nested repository
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Adding a nested repository with Git Submodule

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

## Connecting a nested repository with Git Integration for Jira app

Connecting a nested repository is similar to adding a plain Git repository through the Git Integration for Jira app.

1.  Go to the **Manage repositories/integration** configuration page.

    *   Pre version 5.x, Jira dashboard **Git** menu ➜ **Manage repositories**.
    *   Version 5+, Jira dashboard **Git** menu ➜ **Manage integrations**.

2.  Connect a nested git repository integration via the following:

    *   Pre version 5.x, click either the **Connect to Git repository** button or the **Git** icon on the integration panel.
    
        ![](/wp-content/uploads/gij-dataccenter-manage-repo-nested-connect-git.png)

    *   Version 5+, click on the **Add integration** button, then click **Plain Git repository** on the list of hosting service or use the **Quick start** panel.

        ![](/wp-content/uploads/gij-datacenter-add-new-integration-version-5x-single-nested.png)

3.  On the following screen, paste the **clone URL of the submodule** from your git service portal.

    ![](/wp-content/uploads/gij-datacenter-connect-single-nested-repo.png)

    *   Pre version 5.x (example above), click **Next** to continue.
    *   Version 5+, click **Add integration** to continue.

4.  On the Authentication screen, the input fields depends on what type of clone URL you’ll be using:

    *   **HTTPS authentication** – Enter your credentials such as username and password. For the password, provide the PAT as the password.

    *   **SSH authentication** – Provide the private ssh key. If your SSH key requires a passphrase, provide that as well.

    ![](/wp-content/uploads/gij-datacenter-connect-single-nested-repo-auth.png)

    For this example, we used the HTTP(S) authentication. Enter Username and PAT (personal access token) as the password. Click Next to proceed or click Add integration (if you are using GIJ 5+).

5.  On the Settings screen, leave all options as is. Click Finish to complete this setup.

    ![](/wp-content/uploads/gij-datacenter-connect-single-nested-repo-setting.png)

&nbsp;

The nested repository configuration is added to the Manage repositories/integrations list.

![](/wp-content/uploads/gij-datacenter-connect-single-nested-repo-list.png)

![](/wp-content/uploads/gij-datacenter-add-new-integration-version-5x-single-nested-list.png)

&nbsp;

### Connecting an integration that contains nested repositories

Adding an integration containing nested repositories is similar to connecting a new integration via the Git Integration for Jira app.

1.  Go to the **Manage repositories/integrations** configuration page.

    ![](/wp-content/uploads/gij-datacenter-add-new-integration-with-nested-repos.png)

2.  For this session, we will use GitLab as an example. Click the **GitLab** full-feature integration icon on the integration panel. The following screen is displayed.

    ![](/wp-content/uploads/gij-datacenter-add-new-integration-with-nested-repo-gitlab.png)

3.  On the Connect screen, enter the required personal access token to continue. Click **Connect** to continue.

    ![](/wp-content/uploads/gij-datacenter-add-new-integration-with-nested-repo-scan.png)

    The Git Integration for Jira Data Center app will scan the remote git service and connect found repositories. Click **Import repositories** to continue.

4.  On the Settings screen, leave all options as is. Click **Finish** to complete this setup.

    ![](/wp-content/uploads/gij-datacenter-add-new-integration-with-nested-repo-settings.png)

&nbsp;

The integration configuration containing nested repositories is added to the Manage integrations list.

![](/wp-content/uploads/gij-datacenter-add-new-integration-with-nested-repo-list.png)

&nbsp;
* * *

[**Prev:** Nested repository](/git-integration-for-jira-data-center/Nested-repository-gij-self-managed)

[**Next:** Edit a nested repository settings](/git-integration-for-jira-data-center/Edit-nested-repository-settings-gij-self-managed)


