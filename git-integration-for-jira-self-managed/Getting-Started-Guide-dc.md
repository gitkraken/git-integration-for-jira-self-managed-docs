---

title: Admin Getting Started Guide
description: Start here as a Jira admin to learn what Git Integration for Jira Data Center shows in Jira issues and which security policies to consider before setup.
product: Git Integration for Jira Data Center
feature: Getting Started
content_type: overview
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2024-10
llms_include: true
tags: [admin guide, issue view, linking commits, project permissions, security restrictions]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "getting-started-guide-dc"
    nav_label: "Admin Getting Started Guide"
    nav_order: 20
    nav_parent: ""
    page_type: "index"
    nav_also: ["getting-started-guide-dc|10|Admin Getting Started Guide"]
    card_icon: "rocket"
    card_color: "purple"
    card_description: "Start here as a Jira admin to learn what Git Integration for Jira Data Center shows in Jira issues and which security policies to consider before setup"
---

Thank you for choosing Git Integration for Jira for Data Center (GIJ)! This guide provides Jira Admins with crucial information for deciding the most effective configuration of Git Integration for Jira.

Consider GIJ a "set it and forget it" app and Jira Admins who read each page of this guide can expect to *save days of configuration rework*. With that, let's get crackin!

---
### What to expect

GIJ will display Commits, Branches, and Pull/Merge requests associated with a specific Jira Issue. The Jira Issue key must be included in the commit message, the Branch name, and the Pull/Merge request title in order for GIJ to link the item to the respective Jira Issue.  
 Please see [Linking Git Commits](https://help.gitkraken.com/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed/) for more details.

**Breakdown of information provided by GIJ in Jira issues:**
![Jira Issue View](/wp-content/uploads/Jira-dc-Issue-Breakdown.png)
**Activity Stream - Git Commits**
1. Git Commits tab in the activity stream, broken down by repository
2. Individual Commit, noted by Developer that made the commit
3. Commit message
4. Commit line change summary by file
5. Link to view Code diff in Jira


**Git Integration Panel**
6. Commit Count
7. Option to Create a branch directly from a Jira Issue. Associated Branches with change comparison count to main repository branch.
8. Option to Create a Pull/Merge request directly from a Jira Issue. Associated Pull/Merge Requests with status

&nbsp;

## Security Restrictions and Policies

> **Warning:** Before configuring the application, we encourage new clients to discuss their team's needs and security concerns and restrictions. Consider whether your team needs to restrict code visibility between Jira projects. You can use <a href='/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed'>Project association permissions</a> to limit visibility between Jira projects.
> <p style='margin-bottom:0px'>Please see <a href='/git-integration-for-jira-cloud/known-performance-limitations-gij-cloud'>Known performance limitations on Cloud</a> and <a href='/git-integration-for-jira-data-center/permissions-gij-self-managed'>Permissions</a> for details on how to limit visibility of GIJ panels/Data between Jira users.</p>

&nbsp;
___

[<b style='background-color:#FFFCC3; padding: 1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: medium;'>NEXT</b>](/git-integration-for-jira-data-center/Getting-Started-Guide-App-operations-and-planning-dc) <a href="/git-integration-for-jira-data-center/Getting-Started-Guide-App-operations-and-planning-dc">Application operations and Integration Structure Planning</a>

