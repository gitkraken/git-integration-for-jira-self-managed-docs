---

title: View integration or repository properties
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
<img src='/wp-content/uplaods/gij-gitserver-gitmgr-view-details-01.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

Click the view <img src='/wp-content/uploads/eye-icon.png' style='margin:0 3px'> icon to see basic git repository details for the selected integration/repository:

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
                <li>It shows <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>UPDATED</b> if <i>Repository Root</i> is configured correctly and the Jira instance can access it.</li>
                <li>It shows the <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>DISABLED</b> status if the connected repository is unchecked.</li>
                <li>It shows <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>REINDEXING</b>, <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>SCANNING</b> or <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>QUEUED</b> during reindexing of the connected repository or tracked folder/repositories.</li>
                <li>It shows <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px; font-size: small;'>ERROR</b> if the connected repository has connection issues with the configured git host.</li>
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
<br>
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

<p>&nbsp;</p>

[**Prev:** SSL verify](/git-integration-for-jira-data-center/ssl-verify-gij-self-managed)

[**Next:** Viewing indexing logs](/git-integration-for-jira-data-center/viewing-indexing-logs-gij-self-managed)


