---

title: Edit integration connection settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Edit integration connection settings page allows admins and managers to configure git settings such as displayed name, folder scanning and repository filter options.

![](/wp-content/uploads/gij-gitcfg-actions-edit-integration-conn-cfg.png)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Click the <b>Switch to...</b> label link to switch to the Integration Feature Settings page and vice versa.
    </div>
    </div>
</div>

&nbsp;

Clicking &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit integration connection settings** opens the configuration page for integration connection. The displayed settings depends on which type of integration you are currently working on.

<img src='/wp-content/uploads/gij-gitserver-edit-integration-conn-cfg.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

Utilize the following options to configure the selected integration:

| Option | Description |
| :--- | :--- |
| _**Display Name**_ | This is the name that will appear on the Repository/Integration column. |
| _**Personal Access Token**_ | If the PAT has expired or changed, enter the new PAT on the provided box.<br><br>When the checkbox is unticked, the Username field is displayed. Providing data to both fields (username and password/PAT) and clicking <b>Update</b> will save and update the integration according to the restriction for a new account on the next reindex.<br><img style="margin:10px 0 8px 0;display:block;max-width:100%;" src="/wp-content/uploads/gij-gitdc-edit-integration-use-pat-option.png" /> |
| _**SSL Verify**_ | The Git Integration for Jira app will enforce/ignore verification of SSL certificated when connecting to a git server. For more information, see [SSL verify](/git-integration-for-jira-data-center/SSL-verify-gij-self-managed). |
| _**TrustFolderStat**_ | When this setting is set to `False`, the objects/pack folder will always be scanned to check for new pack files. If set to `True`, the `last-modified` attribute of the folder will be used instead to check the folder for modifications.<div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">The default value for Jira Server is <code>True</code>. For Jira Data Center, it's <code>False</code>.</div></div></div><div class="bbb-callout bbb--note"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your repository is stored on a network share, it is highly recommended to set this option to <code>False</code>.</div></div></div> |
| _**Custom API Path**_ | The Git Integration for Jira app supports this feature for GitHub and GitLab integrations. For more details, see [Working with Custom API Path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed). |
| _**JMESPath Filters**_ | JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. For more information, see [Working with JMESPath Filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed). |

&nbsp;
* * *

[**Prev:** Show tracked or integration repositories](/git-integration-for-jira-data-center/show-tracked-or-integration-repositories-gij-self-managed)

[**Next:** Edit integration feature settings](/git-integration-for-jira-data-center/edit-integration-feature-settings-gij-self-managed)

