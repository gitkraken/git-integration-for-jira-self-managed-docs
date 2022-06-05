---

title: View integration or repository properties
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397673/gitserver-gitmgr-view-details-01.png?version=1&modificationDate=1630642852300&cacheVersion=1&api=v2&width=550&height=190)

Click the view <img src='https://api.media.atlassian.com/file/0a00d402-30e1-429e-8199-46d9a56d9493/image?collection=emoji-site-12f8cd86-3426-4c5c-aced-596093860704&width=38&height=32&max-age=31536000'> icon to see basic git repository details for the selected integration/repository:

<table>
    <thead>
      <tr>
        <th><b>Column</b></th>
        <th><b>Description</b></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><i><b>Status</b></i></td>
        <td>
            This is the repository connection status.
            <ul>
                <li>It shows <b>UPDATED</b> if <i>Repository Root</i> is configured correctly and the Jira instance can access it.</li>
                <li>It shows the <b>DISABLED</b> status if the connected repository is unchecked.</li>
                <li>It shows REINDEXING, SCANNING or QUEUED during reindexing of the connected repository or tracked folder/repositories.</li>
                <li>It shows ERROR if the connected repository has connection issues with the configured git host.</li>
            </ol>
        </td>
      </tr>
      <tr>
        <td><i><b>Last Indexed</b></i></td>
        <td>This is the date and time when synchronization was last executed.</td>
      </tr>
      <tr>
        <td><i><b>Host URL</b></i></td>
        <td>Displays the host URL of the connected integration/repository.</td>
      </tr>
      <tr>
        <td><i><b>Account</b></i></td>
        <td>This is shown for connected AWS integration.</td>
      </tr>
      <tr>
        <td><i><b>Repository Root</b></i></td>
        <td>This is shown if a connected integration is a single
        repository.&lt;br&gt;&lt;br&gt;This is the local path to the repository on the server where
        your Jira service is running.</td>
      </tr>
      <tr>
        <td><i><b>Repository Origin</b></i></td>
        <td>This is shown if the connected integration is a single
        repository.&lt;br&gt;&lt;br&gt;This is the URL to the hosted git service used on the
        project.</td>
      </tr>
      <tr>
        <td><i><b>Changeset, File Added, File Modified, and File Deleted
        formats</b></i></td>
        <td>This is shown if the connected integration is a single repository and web linking is
        also configured.&lt;br&gt;&lt;br&gt;Displays the web linking format strings <i>(if set in
        the repository web linking configuration)</i>.</td>
      </tr>
    </tbody>
  </table>

| **Column** | **Description** |
| --- | --- |
| _**Status**_ | This is the repository connection status.<br><ul><li>It shows <b style='color: green'>UPDATED</b> if <i>Repository Root</i> is configured correctly and the Jira instance can access it.</li><li>It shows the <b style='color: #BBA4FF'>DISABLED</b> status if the connected repository is unchecked.</li><li>It shows <b style='color: #FFC75F'>REINDEXING</b>, <b style='color: #498CFF'>SCANNING</b> or <b>QUEUED</b> during reindexing of the connected repository or tracked folder/repositories.</li><li>It shows <b style='color: #FF565C'>ERROR</b> if the connected repository has connection issues with the configured git host.</li></ol> |
| _**Last Indexed**_ | This is the date and time when synchronization was last executed. |
| _**Host URL**_ | Displays the host URL of the connected integration/repository. |
| _**Account**_ | This is shown for connected AWS integration. |
| _**Repository Root**_ | This is shown if a connected integration is a single repository.<br><br>This is the local path to the repository on the server where your Jira service is running. |
| _**Repository Origin**_ | This is shown if the connected integration is a single repository.<br><br>This is the URL to the hosted git service used on the project. |
| _**Changeset, File Added, File Modified, and File Deleted formats**_ | This is shown if the connected integration is a single repository and web linking is also configured.<br><br>Displays the web linking format strings _(if set in the repository web linking configuration)_. |

<br>
<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The displayed repositories can be sorted by clicking the corresponding list header. The Git Integration for Jira app will remember the sorting choice per user.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Repository Browser will not display the repository if it is disabled in the Git Repositories configuration. The commits and code diffs in the <b>Issue</b> ➜ <b>Git Commits</b>, <b>Git Roll Up</b> and <b>Project</b> tabs will also be unavailable due to this.
    </div>
    </div>
</div>

