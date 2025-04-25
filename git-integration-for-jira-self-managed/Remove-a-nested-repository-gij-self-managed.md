---

title: Removing a nested repository
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        You can only remove a nested git repository settings if it’s a standalone integration.
    </div>
    </div>
</div>

## Pre-GIJ version 5.x.x

Go to the Manage integrations configuration page and choose an integration with the nested repository to remove.

1.  Click &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Remove repository**.

    ![](/wp-content/uploads/gij-datacenter-pre-5x-actions-remove-nested-repo.png)

2.  The following screen is displayed.

    ![](/wp-content/uploads/gij-datacenter-pre-5x-remove-nested-repo-prompt.png)

    Leave the option as is to also remove cloned repository files from the Jira server.

    Uncheck this option if you want to keep the cloned git repository files in the Jira server.

3.  To finish this process, click **Remove** to delete the git repository settings from the Manage integration list.

&nbsp;

## GIJ version 5.x

Go to the Manage repositories configuration page and navigate to the nested repository you want to manage.

1.  For that nested repository, Click &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Disconnect integration**.

    ![](/wp-conent/uploads/gij-datacenter-5x-disconnect-nested-repo.png)

2.  The following screen is displayed.

    ![](/wp-contgent/uploads/gij-datacenter-5x-disconnect-nested-repo-prompt.png)

    Leave the option as is to also remove cloned repository files from the Jira server.

    Uncheck this option if you want to keep the cloned git repository files in the Jira server.

3.  To complete this process, click **Disconnect integration** to remove the git repository settings from the Manage integration list.


&nbsp;
* * *

[**Prev:** Edit nested repository settings](/git-integration-for-jira-data-center/edit-nested-repository-settings-gij-self-managed)

[**Next:** SSL verify](/git-integration-for-jira-data-center/ssl-verify-gij-self-managed)


