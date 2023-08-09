---

title: Permissions
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Depreciation notes</b>
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.0+</b> -- We are dropping support for Jira 7.x.x.<br>
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 3.5.1+</b> -- Dropped support for Internet Explorer 11 browser.<br>
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 2.13.0+</b> -- We are dropping support for Java 7, Jira 6.3 and 6.4.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Universal Plugin Manager 2.2</b> or later is required to properly install this app.
    </div>
    </div>
</div>

&nbsp;

### Permissions Requirement to Display Commit Information

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/ynjggc2wzg?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:12px;margin-bottom:30px;'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/ynjggc2wzg'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Users must have ‘<b><i>View Development Tools</i></b>’ permission in order to view commit information on the issue page.
        <div class="nextpara">
            Administrators must grant themselves the ‘<b><i>View Development Tools</i></b>’ permission in order to view commit information on the issue pages.</div>
        </div>
    </div>
</div>

The user needs to be in the developers group to view code diffs when default permission scheme is used.

![](/wp-content/uploads/gij-docs-permissions-view-dev-tools-project-acl-c.png)

Consider the following criteria when setting permissions:

*   Permission name may be different depending on your version of Jira.

*   Project permissions are configured on the project administration page. Different projects may have different permissions.

*   Default permission scheme grants access to add-on to all members of _**administrators**_ and _**developers**_ groups. No additional configuration is required in this case.

