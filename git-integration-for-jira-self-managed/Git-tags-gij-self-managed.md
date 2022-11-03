---

title: Git tags
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Git Integration for Jira app supports both lightweight and annotated tags. The tags are loaded separately from the rest of the Git Source Code.

## Introduction

Git tags identify specific release versions of your code in a particular branch and do not change when the branch moves on. A tag is an alias for a commit hash, much like symbolic names for a given revision. It is typically used to mark a particular point in the commit. It is like a branch with a read-only attribute. The git tags are accessible in the developer panel.

The git tags refers to merged, released work.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Having more than one tag with the same name across different branches can become difficult to maintain.
    </div>
    </div>
</div>

Tags cannot be moved since it is linked to a specific commit and are not pushed by default. 

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Create a branch to start working from it if a tag is checked out.
    </div>
    </div>
</div>
<br>

The Git for Jira app supports two types of git tags:

*   **lightweight**  –  shows only the commit object

*   **annotated**  –  shows the message, author and the tag object followed by the commit

<br>

A lightweight tag can be use for marking a version or some specific commits that you will need to use later on  —  like a temporary object label. It does not contain extra information.

Annotated tags can contain a message, author and date different than the commit that they are pointing to  —  like describing a release without making a release commit.

## Getting started

The git tag is displayed on the right sidebar if it is enabled in the [General Settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed) of the Git Integration app ➜ `Calculate and show Git tags in Git Source Code panel`.

<br>

<img src='/wp-content/uploads/gij-dev-panel-git-tags-gen-cfg-setting.png' width=550 height=68 style='display:block;margin:25px auto;max-width:100%' />

This feature is disabled by default for existing integrations and is automatically enabled for new integrations.

<br>

<img src='/wp-content/uploads/gij-git-tags-example.png width=134 height=132 style='display:block;margin:25px auto;'/>

<br>

The Git Integration for Jira app will show the last 3 and first tags if no filter is set. If the filter is set, the Git Integration for Jira app will use it and will display the tags sorted in ascending order by date.

If there are several git tags listed, click the **more...** label link to expand the list in increments of five tags.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Notification</b><br>
        If loading of tags on a Jira issue takes longer than 60 seconds, the Git Integration app will notify the user about it and aborts the operation. This could happen if the Jira issue contains several hundreds of git tags or more.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Cached Tags</b><br>
        Git tags and branches are cached for the most recently viewed 1000 Jira issues (across all Jira projects). The cache is reset each time a new change in any repository is detected. The cache is built the first time an issue with a tag and/or branch is loaded by a user. Thus, subsequent loading of Jira issues with tag or branch information will utilize cached values.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The tag calculation timeout is <b>86400</b> seconds.
    </div>
    </div>
</div>
<br>

## Tag information

<img src='/wp-content/uploads/gij-gitserver-git-tags-hover.png' width=334 height=221 style='display:block;margin:25px auto;max-width:100%' />

<br>

Move the mouse pointer over the tag to display the following tooltip information:

*   Repository Name

*   Date / Time

*   Commit author name and email address (if available)

*   Message (if any)


## Tag associations

Tags are only associated with the Jira issue by Jira keys that are specified in commits that belong to the tag. Specifying a Jira key in the name of a tag does not associate this tag with the mentioned ticket.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If some commits relate only to tags, these commits will not be displayed. For more information, see the <a href='/git-integration-for-jira-data-center/Known-issues#commits-relating-only-to-tags-are-not-displayed-gij-self-managed'>related known issue</a>.
    </div>
    </div>
</div>
<br>

## Reindexing tags

For users who have the 'Calculate and show Git tags' option turned **off**, There is a safe way on how to turn this setting on. Do note that the following steps should be done outside business operating hours to avoid impacting Jira users:

1.  Turn on the `Calculate and show Git tags` in **General settings**.

2.  Manually reindex the repository(s) with the highest number of tags. The resulting reindexing time –- is the maximum reindexing time for the tags. The subsequent reindexing times will be much less due to the tags incremental reindex. This can be verified by running the repository reindex a second time.

3.  **If the resulting reindexing time is acceptable** -- perform reindexing of all other repositories (for example, using ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Reindex all**).

4.  **If the resulting reindexing time is not acceptable** –- the tags structure is probably too complex for the plugin, and the **Calculate and show Git tags** setting should be left as **OFF**.

<p>&nbsp;</p>

<br>
<br>

[**Prev:** Jira Git integration development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed)

[**Next:** Jira project page](/git-integration-for-jira-data-center/jira-project-page-gij-self-managed)


