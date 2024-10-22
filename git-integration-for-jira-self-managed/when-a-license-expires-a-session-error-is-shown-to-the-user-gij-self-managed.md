---

title: When a GIJ license expires, it shows up as a session error to the user
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

### Problem

I'm getting an error message that says it's a session error, `SessionTokenNotFoundException`, and I cannot proceed to use any GIJ features anymore.

&nbsp;

### Diagnosis

While session errors can just go away when the page is reloaded, this specific session error still remains. Jira admins will see a message similar to the one below:

![](/wp-content/uploads/gij-dc-cloud-session-token-not-found-error.png)

&nbsp;

### Solution

Session error message that persist can mean that the trial or license to GIJ had expired. GIJ can detect a license expiration before it tries to detect a valid session. When valid, GIJ will display the correct message about the current license status.

Once you have renewed you Git Integration for Jira app license, this error message

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-cloud/gij-cloud-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>
<br>

