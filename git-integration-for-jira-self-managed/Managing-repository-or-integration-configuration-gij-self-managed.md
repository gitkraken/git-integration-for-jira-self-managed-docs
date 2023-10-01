---

title: Managing repository or integration configuration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Manage connected repositories or integration via the ![](/wp-content/uploads/actions-icon.png) **Actions** commands on the git configuration page.

### Introduction

After successfully connecting your git repositories or integrating your git host via Git Integration for Jira app, you can change repository settings depending on the connection protocol of the repository or integration.

&nbsp;

### Getting started

On the git repository configuration page, you can manage connected repositories and integration such as enabling/disabling repository connection/integration (Jira Server only), edit/update repository/integration settings or disconnect repositories/integrations.

<img src='/wp-content/uploads/gij-manage-repositories-list-server.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

### Repository/integration list

For the repository/integration list, utilize the following references for the column items:

<table>
    <thead style='text-align:left;'>
        <tr>
            <th style="width:16%">Column</th>
            <th>Description</th>
            <th style="width:16%">Platform</th>
        </tr>
    </thead>
    <tbody style='text-align:left;'>
        <tr>
            <td><b><i>Enabled</i></b></td>
            <td>Enables/disables an integration for use in Jira. For disabled integrations, repository information and function such as commits, pull/merge request, git viewer and etc. are not available.</td>
            <td>JIRA SERVER<br>DATA CENTER</td>
        </tr>
        <tr>
            <td><b><i>Location</i></b></td>
            <td>
                Displays a short identifier where the integration is located. For example, Some supported git host integration are also displayed here.
            </td>
            <td>JIRA SERVER<br>DATA CENTER</td></td>
        </tr>
        <tr>
            <td><b><i>Repository / Integration</i></b></td>
            <td>
                Displays the repository name, integration name or integration URL.<br>
                <div class="bbb-callout bbb--info" style='margin-bottom:0px !important'>
                    <div class="irow">
                        <div class="ilogobox">
                            <span class="logoimg"></span>
                        </div>
                        <div class="imsgbox">
                            While you can change the name displayed for this column, some integration names does not allow to be changed.
                        </div>
                    </div>
                </div>
            </td>
            <td>JIRA SERVER<br>DATA CENTER<br>JIRA CLOUD</td>
        </tr>
        <tr>
            <td><b><i>Last indexed</i></b></td>
            <td>Shows how long the time the integration was last indexed.</td>
            <td>JIRA SERVER<br>DATA CENTER</td>
        </tr>
        <tr>
            <td><b><i>Last indexer check</i></b></td>
            <td>
                Shows the date and time the indexing service has checked if the repository should be examined for changes.<br><br>For more information on Jira Cloud indexer, see <a href="/git-integration-for-jira-cloud/jira-cloud-indexing-explainer-gij-cloud">Jira Cloud: Indexing Explainer</a>.
            </td>
            <td>JIRA CLOUD</td>
        </tr>
        <tr>
            <td><b>Status</b></td>
            <td>
                Shows the index status of the integration.<br>
                <ul style='margin-bottom:0px;'>
                    <li>
                        It shows <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>UPDATED</b> if <i>Repository Root</i> is configured correctly and the Jira instance can access it.
                    </li>
                    <li>
                        It shows <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>REINDEXING</b>, <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>RUNNING</b>, or<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>QUEUED</b> during reindexing of the connected repository or tracked folder/repositories.
                    </li>
                    <li>
                        It shows <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px; font-size: small;'>ERROR</b> if the connected repository has connection issues with the configured git host.
                    </li>
                </ul>
            </td>
            <td>JIRA SERVER<br>DATA CENTER<br>JIRA CLOUD</td>
        </tr>
        <tr>
            <td><b><i>Actions</i></b></td>
            <td>
                To the right of the <b>Status</b> column are actions that can be performed for the selected connected repository/integration.<br><br>Clicking the Actions <img src='/wp-content/uploads/actions-icon.png' /> icon will open a context menu with a set of functions for managing integrations. The Actions sub-menu functions will depend on the type of integration you were working on.<br><br>For more information, see <b>Managing Integration via Actions</b> for your specific platform:<br>
                <ul style='margin-bottom:0px;'>
                    <li><a href='/git-integration-for-jira-cloud/managing-integrations-via-actions-jira-cloud-gij-cloud'>Jira Cloud</li>
                    <li><a href=''>Jira Server/Data Center</li>
                </ul>
            </td>
            <td>JIRA SERVER<br>DATA CENTER<br>JIRA CLOUD</td>
        </tr>
    </tbody>
</table>

&nbsp;

[**Prev:** Self-signed HTTPS integration](/git-integration-for-jira-data-center/self-signed-https-integration-gij-self-managed)

[**Next:** Managing integration via Actions](/git-integration-for-jira-data-center/managing-integration-via-actions-gij-self-managed)

&nbsp;

### More related topics on setting up repositories

[Git integration configuration page](/git-integration-for-jira-data-center/git-integration-configuration-page-gij-self-managed)

[Using the Add new integration wizard](/git-integration-for-jira-data-center/using-the-add-new-integration-wizard-gij-self-managed)

[Using the Connect Repository wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed)

[Connecting a repository via Advanced setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed)

[Adding a repository hosted on Windows Server or Windows Network Share](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-server-or-windows-network-share-gij-self-managed)

[Setup repository root not located in Jira HOME directory](/git-integration-for-jira-data-center/setup-repository-root-not-located-in-jira-home-directory-gij-self-managed)

[Tracked folders overview](/git-integration-for-jira-data-center/tracked-folders-overview-gij-self-managed)

[Self-signed HTTPS integration](/git-integration-for-jira-data-center/self-signed-https-integration-gij-self-managed)

**Managing repository or integration configuration** (this page)

[Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed)


