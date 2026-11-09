---

title: Smart commits - Workflow transitions
description: "Learn how smart commits map to workflow transition and status names, which characters are valid, and how admins should name transitions."
product: Git Integration for Jira Data Center
feature: Smart Commits
content_type: concept
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-08
llms_include: true
tags: [workflow transitions, transition names, status names, smart commits, valid characters]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Smart commits – Workflow transitions"
    nav_order: 30
    nav_parent: "smart-commits-gij-self-managed"
    page_type: "content"
---

The simple Jira workflow does not contain explicit transition names. These kind of workflow with no explicit transition names are becoming more popular as Atlassian is suggesting them to administrators upon project creation.

<img src='/wp-content/uploads/gij-jira-simple-workflow.png' width=217 height=232 style='display:block;margin:25px auto;max-width:100%' />

The name of the status is the transition. So, using the basic example above, the valid transitions from DONE are:

*   `#to-do`

*   `#in-progress`

*   `#in-review`

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

&nbsp;

<br>
<br>

[**Prev:** Smart commit - Advanced examples](/git-integration-for-jira-data-center/advanced-examples-gij-self-managed)

[**Next:** Viewing workflows](/git-integration-for-jira-data-center/viewing-workflows-gij-self-managed)


