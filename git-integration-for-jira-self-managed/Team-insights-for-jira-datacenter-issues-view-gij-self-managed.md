---

title: Issues View - TIJ DC 
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/tij-datacenter-issues-view-start.png)

The default view for the Team Insights for Jira app is the Issues View.

You can switch to another view such as Issues or Epics by clicking their specific tabs. In Issues View, the epics issue list can be displayed along with the other general Jira issues.

Use the search bar together with available search options to filter the list view.

&nbsp;

### Column Information

The list view displays Jira issues showing priority, user activity, and other information:

| Column | Description |
| :--- | :--- |
| **Issue** | The Issue column shows the Jira issues that contain user and progress activities. |
| **Priority** | Displays the degree of priority of a Jira issue. |
| **Status** | Shows the progress status of a Jira issue. |
| **Assignee** | Shows the user the Jira issue is currently assigned to. |
| **Contributors** | Shows the contributor users actively worked on the Jira issue. |
| **Sprint** | Shows the sprint name a Jira issue is included in. |
| **Days** | Shows the number of days a Jira issue has been worked on. |
| **Comments** | Shows the number of comments a Jira issue has. |
| **Commits** | Shows how many commits this task has.<br><div class="bbb-callout bbb--alert"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your organization or team requires information be displayed in this column, install the Git Integration for Jira DC app.</div></div></div> |
| **Pull requests** | Shows how many pull requests this task has.<br><div class="bbb-callout bbb--alert"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your organization or team requires information be displayed in this column, install the Git Integration for Jira DC app.</div></div></div> |
| **Code \+\/\-** | Shows the numerical value indicating the number of lines of code changes. |

&nbsp;

### Showing Issue Details

To view more details about a specific Jira issue or Epics, click on the twisty icon (**\>**) to expand it.

![](/wp-content/uploads/tij-datacenter-issue-view-details.png)

Hover on the Issue details icon to display the detailed dialog of the Jira issue.

![](/wp-content/uploads/tij-datacenter-issue-view-details-dialog.png)

The issue details shows the following information on:
*   who the Jira issue is assigned to
*   which Jira issues the current ticket is waiting on
*   which Jira issues are causing the current ticket to stall
*   what is the current state of the Jira issue

&nbsp;

### Sprints view

On the right of the Issue list is the sprints view, showing the sprint timeline. This provides team managers the graphical view of the progress of the Jira issues and will be able to plan what to do next. They can also identify issues needing attention and see which team members are overloaded or have approaching due dates.

![](/wp-content/uploads/tij-datacenter-issue-view-timeline.png)

The red line indicates today’s date. If you drag the timeline scrubber, it changes the Activity date range filter. Hence, it will only show issues that have activity in that time frame. For example, dragging the slider to left lets you take a peek on what was worked on in the past few days or yesterday.

Hover the mouse pointer over the activity bar and it will show details about status changes, and statistics on development changes – for that day. This will display what type of work the team performed on that day.

![](/wp-content/uploads/tij-datacenter-issue-view-timeline-activity-details.png)

Click on the **Go to issue** shortcut to take you directly to that Jira issue.

Scroll the timeline horizontally by using the scrollbar at the bottom page of the browser. The timeline shows a list of issues based on your selected Issue and Activity filters.

Click on an Issue row to expand child issues and view additional information by moving the mouse pointer over the revealed icons.

![](/wp-content/uploads/tij-datacenter-issue-view-timeline-row-details.png)

Finally, on the bottom part of the page, you will see the following shortcut controls if the list exceeds 25 rows:

| Control | Description |
| :--- | :--- |
| **Displayed items** | Set how many items per page will be displayed in the list view. |
| **Page navigation** | Shows the page controls to switch across several pages of information views. |
| Today | Clicking this button will automatically adjust the slider to today’s date. |
| <img src="/wp-content/uploads/gij-question-mark-icon-32.png" style="height:16px;width:auto"> | Clicking this button will show quick helpful tips on how to navigate and use the General, Epics, or Teams view. |

&nbsp;

### Search Functions and Filters

On the search panel, team/project managers can set the criteria and apply some filters to the search.

#### Activity filter

![](/wp-content/uploads/tij-datacenter-issue-view-search-panel.png)

Set **Activity Dates** by choosing the desired interval. Click on the drop-down list to see available intervals which include:

*   All Activity – Last 4 weeks
*   Last 2 weeks
*   Last 1 week
*   Custom – Select start date and end date for this filter.

For **Filters**, select if you want to:

*   Show Issues with Jira Activity, and/or
*   Show Issues with Git Activity (requires Git Integration for Jira Data Center app installed)

You can either one or both.

For **Contributors**, click on the drop-down list to select one or more members for this filter. The default filter is **All**. Utilize the search box to quickly find the team member that you want to select for this filter.

To reset selection and filter settings click **Clear** for each filter group.

#### Issue filter

The Issue Filters allows team/project managers to assign available issue filters to the search. Utilize the search box on each filter to quickly find and select one or more categories.

| Category filter | Description |
| :--- | :--- |
| Project | Select one or more projects for the issue filter. |
| Sprints | Click on the sprints filter to view and select one or more sprints.<br>Choose **No Sprint** if you want to see projects that does not have sprints. |
| Statuses | Select one or more statuses for the issue filter. |
| Assignees | Select one or more team members for the issue filter.
| Labels | Select one or more labels for the issue filter. |
| Issue Types | Select one or more issue type for the issue filter. |
| Versions | Select one or more versions for the issue filter. Displays nothing if no versions are detected. |
| Priorities | Select one or more priority state for the issue filter. |
| Components | Select one or more components for the issue filter. Displays nothing if no components are detected. |

#### Clear All

To clear all the selected filters and search settings, click **Clear All**. Some selections and search filters are also reset to default.

With all the selection of filters and search options in place, click **Search** to see the results in the list view according to your preference.

