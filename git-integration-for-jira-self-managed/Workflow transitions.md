---

title: Smart commits - Workflow transitions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The simple Jira workflow does not contain explicit transition names. These kind of workflow with no explicit transition names are becoming more popular as Atlassian is suggesting them to administrators upon project creation.

<img src='https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398464/jira-simple-workflow.png?version=1&modificationDate=1630642890131&cacheVersion=1&api=v2&width=217&height=232' class='center img-responsive img-bordered' />

The name of the status is the transition. So, using the basic example above, the valid transitions from DONE are:

*   **#to-do**

*   **#in-progress**

*   **#in-review**

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Transition names</b><br>
        The workflow transition names must be unique.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Absence of transition names</b><br>
        When there are no transition names — just use the status names. If there is a space, replace it with "–" (hyphens). For example, <code>CODE REVIEW</code> becomes <code>#code-review</code>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Commit authors</b><br>
        Only letters and "-" (dash) are valid for workflow transition names for smart commits. Any other characters are treated as invalid. Smart commits will ONLY use the valid characters before the occurrence of an invalid character for processing.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Jira Administrators</b><br>
        When adding transitions in the Workflow editor, make transition names simple and easy to remember. Only use letters and only one space between words.
    </div>
    </div>
</div>

