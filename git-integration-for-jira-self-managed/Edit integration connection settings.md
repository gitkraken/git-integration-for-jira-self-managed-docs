---

title: Edit integration connection settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397536/gitcfg-actions-edit-repo-conn-cfg.png?version=1&modificationDate=1630642845462&cacheVersion=1&api=v2&width=680&height=213)

Clicking  <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration connection settings** opens the configuration page for integration connection settings.
\
\
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397536/gitserver-edit-integration-conn-cfg.png?version=1&modificationDate=1630642844991&cacheVersion=1&api=v2&width=680&height=514)

Utilize the following options to configure the selected integration:

| **Option** | **Description** |
| :--- | :--- |
| _**Display Name**_ | This is the name that will appear on the Repository/Integration column. |
| _**Personal Access Token**_ | If the PAT has expired or changed, enter the new PAT on the provided box. |
| _**SSL Verify**_ | The Git Integration for Jira app will enforce/ignore verification of SSL certificated when connecting to a git server. For more information, see [SSL verify](/git-integration-for-jira-self-managed/SSL-verify). |
| _**TrustFolderStat**_ | When this setting is set to `False`, the objects/pack folder will always be scanned to check for new pack files. If set to `True`, the `last-modified` attribute of the folder will be used instead to check the folder for modifications.<div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">The default value for Jira Server is <code>True</code>. For Jira Data Center, it's <code>False</code>.</div></div></div><div class="bbb-callout bbb--note"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your repository is stored on a network share, it is highly recommended to set this option to <code>False</code>.</div></div></div> |
| _**Custom API Path**_ | The Git Integration for Jira app supports this feature for GitHub and GitLab integrations. For more details, see [Working with Custom API Path](/git-integration-for-jira-self-managed/working-with-custom-api-path/). |
| _**JMESPath Filters**_ | JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. For more information, see [Working with JMESPath Filters](/git-integration-for-jira-self-managed/working-with-jmespath-filters/). |

