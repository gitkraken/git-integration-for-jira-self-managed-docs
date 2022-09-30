---

title: Email Support
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
If you need help with the Git Integration for Jira app, please e-mail us: [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com).

Please include the "Support Zip" that Jira produces for diagnosing issues.

Also include information about:

*   How long have you been experiencing this problem?

*   If there were any changes to the environment that would be notable?


You can produce the "Support Zip" by following the steps in [this article](/git-integration-for-jira-data-center/how-to-create-the-support-zip-file-gij-self-managed) or by accessing `http://[JiraServerNameHere]/plugins/servlet/troubleshooting/view/`.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        Jira Cloud does not have the Support Zip feature.
    </div>
    </div>
</div>
<br>

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/thbjckk3kv?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div styel='text-align: center; margin-top: 10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/thbjckk3kv'><b>here</b></a> to open this video in a new browser tab for more viewing options</i>.
</div>
<br>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Export Jira Support Zip settings to get the best support.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the support zip is larger than 15 MB _(too large for our support system to receive by email) -_ contact us: <a href='mailto:support@gitkraken.com'>support@gitkraken.com</a> and we will provide a secure location to upload the support zip.
    </div>
    </div>
</div>
<br>

## Memory warnings before GC

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b> <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.0</b>

This type of information can be obtained from the logs.

The memory warnings are added to the logs before GC tasks. This provides admins a window for monitoring memory issues. The following data is logged if the threshold is met:

*   amount of free memory in the Java Virtual Machine in bytes;

*   summary size of index files in bytes (for cloned repositories).


Administrators can view these logs and do maintenance routines if needed. You may send the logs to our support email for further analysis.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Log settings</b><br>
        In order to see the log messages, you need to be sure that the logger severity for <code>'com.bigbrassband.jira.git.jiraservices.jobs'</code> (Jira settings ➜ System) is set up on the <b>INFO</b> or lower (please check it on <code>http://&lt;server&gt;/jira/secure/admin/ViewLogging.jspa</code> – <i>Jira settings ➜ Logging and profiling</i>).
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app will automatically use the WARN logger severity if the memory size tolerance has been reached. If administrators doesn't want to see such logs in all GC runs, apply the WARN severity level.
    </div>
    </div>
</div>

