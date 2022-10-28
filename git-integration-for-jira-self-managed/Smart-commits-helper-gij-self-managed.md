---

title: Smart commits helper
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The smart commit helper is available at the following locations in Jira:

*   Issue ➜ **Git Commits tab**

*   Projects (sidebar) ➜ **Git Commits**

*   Repository Browser (View all repositories) ➜ click a repository ➜ **Latest commits**


<img src='/wp-content/uploads/gij-smart-commit-helper-example.png' style='display:block;margin:25px auto;max-width:100%' />


A smart commit helper indicator is displayed to the right of the user/commit author:

| **Status** | **Description** |
|:-----------|:----------------|
| <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>COMMIT<b> | The Smart Commits setting is enabled for the repository but there is no smart commit keyword in the commit message. |
| <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>SMART COMMIT</b> | The commit message has a valid smart commit structure and was successfully  |
| <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>SMART COMMIT ERROR</b> | There was an error during smart commit processing. For example, invalid keyword; commit author and Jira user are not the same; permission issues or wrong values. |

<br>

**The smart commit helper status are not shown:**

*   for any smart commits that were made before <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 2.9.3</b> of Git Integration for Jira app.

*   for smart commits that were ignored due to **Smart commits** setting for that repository is disabled.

*   for smart commits that have not been processed yet.

*   for processed commits with ticket ID but without smart commit keyword when **Smart commits** setting is disabled for that repository.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        When <b>Smart commits</b> setting is <code>Disabled</code> for that repository, the Git Integration for Jira app will not show the COMMIT indicators.
    </div>
    </div>
</div>
<br>

Refer to the commit message case examples below:

| **Commit ID** | **Commit Message** |
| :--- | :--- |
| Commit1 | Merged to master<br>(This commit message does not contain a Jira issue key) |
| Commit2 | **TST-1** Merged to master<br>(This commit message has a Jira issue key but does not have a smart commit keyword) |
| Commit3 | **TST-1** Merged to master **#done**<br>(This commit message has an issue key and a valid smart commit transition keyword) |
| Commit4 | **TST-1** Merged to master **#unknownSCkeyword**<br>(This commit message has an invalid smart commit keyword) |

<br>

**When Smart commits setting (SC) was set to ENABLED:**

| **Commit ID** | **Status after SC=Disabled** | **Status after SC=Enabled** |
| :--- | :--- | :--- |
| Commit1 | Commit is ignored since issue key is not provided. | Commit is ignored since issue key is not provided. |
| Commit2 | No status indicator. | <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>COMMIT</b> |
| Commit3 | <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>SMART COMMIT</b> | <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>SMART COMMIT</b> |
| Commit4 | <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>SMART COMMIT ERROR</b> | <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>SMART COMMIT ERROR</b> |

<br>

**When Smart commits setting (SC) was set to DISABLED:**

| **Commit ID** | **Status after SC=Disabled** | **Status after SC=Enabled** |
| :--- | :--- | :--- |
| Commit1 | Commit is ignored since issue key is not provided. | Commit is ignored since issue key is not provided. |
| Commit2 | No status indicator. | No status indicator because it was marked as ignored. |
| Commit3 | No status indicator. | No status indicator because it was marked as ignored. |
| Commit4 | No status indicator. | No status indicator because it was marked as ignored. |

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The commit status shown on the Issue page depends on the <b>Smart commits</b> setting that was set at the time the commits were processed.
    </div>
    </div>
</div>

<p>&nbsp;</p>

<br>
<br>

[**Prev:** Viewing workflows](/git-integration-for-jira-data-center/viewing-workflows-gij-self-managed)

[**Next:** Smart commits General setting](/git-integration-for-jira-data-center/smart-commits-general-setting-gij-self-managed)


