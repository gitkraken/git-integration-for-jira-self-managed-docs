---

title: GIJ Data Center Getting Started Guide
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Application Overview
---
### What to expect

Thank you for choosing Git Integration for Jira Data Center (GIJ)! This guide provides Jira Admins with crucial information for deciding the most effective configuration of Git Integration for Jira for their specific needs.

GIJ will display Commits, Branches, and Pull/Merge requests associated with a specific Jira Issue. The Jira Issue key must be included in the commit message, the Branch name, and the Pull/Merge request title in order for GIJ to link the item to the respective Jira Issue.  
 Please see [Linking Git Commits](https://help.gitkraken.com/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed/) for more details.

**Breakdown of information provided by GIJ in Jira issues:**
![Jira Issue View](/wp-content/uploads/Jira-Issue-Breakdown.png)
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




## Security Restrictions and Policies
---
<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
Before configuring the application, we encourage new clients to discuss their team's needs and security concerns and restrictions. Consider whether your team needs to restrict code visibility between Jira projects. You can use <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed/'>Project association permissions</a> to limit visibility between Jira projects. 

Please see <a href='/[git-integration-for-jira-cloud/known-performance-limitations-gij-cloud/](https://help.gitkraken.com/git-integration-for-jira-data-center/permissions-gij-self-managed)'>Permissions</a> for details on how to limit visibility of GIJ panels/Data between Jira users.
    </div>
    </div>
</div>
___

[<b style='background-color:#FFFCC3; padding:1px 5px; color:#181D28; border-radius:3px; margin: 0 5px; font-size: small;'>NEXT</b>](/git-integration-for-jira-data-center/Getting-Started-Guide-App-operations-and-planning-dc) <a href="https://help.gitkraken.com/git-integration-for-jira-data-center/Getting-Started-Guide-App-operations-and-planning-dc/">Application operations and Integration Structure Planning</a>