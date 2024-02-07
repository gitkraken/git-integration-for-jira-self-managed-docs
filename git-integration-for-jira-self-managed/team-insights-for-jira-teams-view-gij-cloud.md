---

title: Teams View (TIJ Cloud)
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

![](/wp-content/uploads/tij-gitcloud-teams-view-main-screen.png)

The Teams View allows team/project managers to see team activities and each row in the list is represented by each member in the team.

&nbsp;

### Member activities

To view the activity information of a team member, click on the row for that team member.

![](/wp-content/uploads/tij-gitcloud-teams-item-details.png)

Information can be monitored in real-time as you inspect each team member listed in the view on…

*   which Jira issues a team member are assigned to
*   which Jira issues a team member has worked on
*   priority of the Jira issues assigned or worked on by a team member
*   how much time was spent on a Jira issue
*   git statistics for each team member (requires Git Integration for Jira app installed)
*   progress and status of each Jira issue under a team member
*   deadlines of the tasks for each member by using the timeline

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        By adopting a task and assignment perspective for each team member, project managers can quickly assess if someone is overloaded with work. This allows them to make necessary adjustments as required.
    </div>
    </div>
</div>

&nbsp;

### Member issue details

On the expanded view on a member in the list, hover on the issue details icon to see a brief information for that Jira issue.

<img src='/wp-content/uploads/tij-gitcloud-teams-view-member-issue-mouse-over.png' style='margin:25px auto 35px auto;max-width:100%;display:block;' />

You can click a Jira issue link on the popup dialog to open it in a new browser tab.

<img src='/wp-content/uploads/tij-gitcloud-teams-view-member-issue-dlg-link.png' style='margin:25px auto 35px auto;max-width:100%;display:block;' />

Click away from the issue details dialog to hide it.

&nbsp;

### Status progress

Similar to what the status column shows in other views, hover on the status column for the selected issue to see the task progress information.

<img src='/wp-content/uploads/tij-gitcloud-teams-view-issue-hover-status.png' style='margin:25px auto 35px auto;max-width:100%;display:block;' />

In this way, team/project managers can plan ahead and see which tasks are currently worked on and monitor the progress of each assignment.

&nbsp;

### Timeline view

![](/wp-content/uploads/tij-gitcloud-teams-view-timeline-gen.png)

Team managers can utilize the timeline view to examine activity boxes for each team member. This feature provides a concise overview of user activities throughout the day, enabling managers to gain a comprehensive understanding of what tasks and projects each team member has been working on.

<img src='/wp-content/uploads/tij-gitcloud-teams-voew-activity-log-show.png' style='margin:25px auto;max-width:100%;display:block;' />

Column information

Refer to the table below describing each column header’s description and what information it shows.

| Column | Description |
|:-------|-------------|
| **_Name_** | This is the name of a team member. Click a row to expand and see activities related to this team member. |
| **_Priority_** | Displays the priority of a Jira issue being worked on by a team member. |
| **_Status_** | Shows status information and progress of a specific task. |
| **_Contributors_** | Displays one or more contributors working on a specific task. |
| **_Assignee_** | Shows the member assigned to this task. |
| **_Days_** | Indicates the time the task has been worked on. |
| **_Comments_** | Shows how many comments this task has. |
| **_Commits_** | Shows how many commits this task has.<br><div class="bbb-callout bbb--alert"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your organization or team requires information be displayed in this column, install the Git Integration for Jira app.</div></div></div> |
| Pull requests | Shows how many pull requests this task has.<br><div class="bbb-callout bbb--alert"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your organization or team requires information be displayed in this column, install the Git Integration for Jira app.</div></div></div> |

### Search functions and filters

On the search panel, team/project managers can set the criteria and apply some filters to the search.

![](/wp-content/uploads/tij-gitcloud-teams-view-search-panel.png)

To find and display items in the list that contain a specific word or text, simply enter the desired search term into the search box. This will allow you to easily locate and view relevant items from the list.

#### Activity Filter

![](/wp-content/uploads/tij-gitcloud-teams-view-search-activity-filter.png)

Set **Activity Dates** by choosing the desired interval. Click on the drop-down list to see available intervals which include:

*   All Activity - Last 8 weeks
*   Last 4 weeks
*   Last 2 weeks
*   Last 1 week
*   Custom - Select which day from now or before for this filter.

For **Filters**, select if you want to:

*   Show Issues with Jira Activity, and/or
*   Show Issues with Git Activity (_requires Git Integration for Jira app installed_)

You can select one or both. Click **Apply selection** to accept the selected filters.

For **Contributors**, click on the drop-down list to select one or more members for this filter. The default filter is **_All_**. Utilize the search box to quickly find team member(s) that you want to choose for this filter. Finally, click **Apply selection** to accept the selected members for the contributors filter.

To reset selection and filter settings click **Clear** on each filter group.

#### Issue Filter

The Issue Filters allows team/project managers to assign available issue filters to the search. Utilize the search box on each filter to quickly find and select one or more categories. If available, click Apply selection to accept the selected filters.

| Category filter | Description |
|:----------------|:------------|
| **_Project_** | Select one or more projects for the issue filter. |
| **_Sprints_** | Click on the sprints filter to view and select one or more sprints.<br><br>Choose **No Sprint** if you want to see projects that does not have sprints. |
| **_Statuses_** | Select one or more statuses for the issue filter. |
| **_Assignees_** | Select one or more team members for the issue filter. |
| **_Labels_** | Select one or more labels for the issue filter. |
| **_Issue Types_** | Select one or more issue type for the issue filter. |
| **_Versions_** | Select one or more versions for the issue filter. Displays nothing if no versions are detected. |
| **_Priorities_** | Select one or more priority state for the issue filter. |
| **_Components_** | Select one or more components for the issue filter. Displays nothing if no components are detected. |

To clear all the selected filters and search settings, click **Clear All**. Some selections and search filters are also reset to default.

With all the selection of filters and search options in place, click **Search** to see the results in the list view according to your preference.

&nbsp;

### More on Team Insights for Jira features

[Team Insights for Jira Cloud](/git-integration-for-jira-cloud/team-insights-for-jira-gij-cloud)

[Sprints/Epics View](/git-integration-for-jira-cloud/team-insights-for-jira-issues-epics-view-gij-cloud/)

**Teams View** (this page)

[Backlog View](/git-integration-for-jira-cloud/team-insights-for-jira-backlog-view-gij-cloud/)

[Pull request timeline reindex](/git-integration-for-jira-cloud/pull-request-timeline-for-tij-gij-cloud/)


