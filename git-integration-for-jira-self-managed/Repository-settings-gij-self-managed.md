---

title: Repository settings (General setting)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.0.1+</b><br>
        This setting is now moved to the <b>Advanced settings</b> in General settings.
    </div>
    </div>
</div>
<br>

<img src='/wp-content/uploads/gij-gitserver-gencfg-repo-max-open-pack-files.png' style='display:block;max-width:100%;margin:25px auto' />

&nbsp;

### Max open pack files count

Set the maximum number of open files the Git Integration for Jira app uses. For new Git Integration for Jira app install or upgrade, the default value is **16**. This is the **recommended** value.

You may set this value higher but NOT EXCEEDING the maximum number of open files allowed in the system.


The maximum number of open files vary for each operating system you are working with. The same units for each OS is used.

For systems that has a lot of connected repositories, increasing this value to a higher setting may improve the performance of the Git Integration for Jira app -- such as during repository browsing. This is also applicable to very busy systems that has large repository connections. Configure the maximum open files allowed by the system accordingly.

