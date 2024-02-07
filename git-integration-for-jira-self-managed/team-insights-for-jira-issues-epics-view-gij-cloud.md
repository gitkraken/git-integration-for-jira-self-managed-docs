---

title: Sprints / Epics View (TIJ Cloud)
description:
taxonomy:
    category: git-integration-for-jira-cloud

---

![](/wp-content/uploads/tij-gitcloud-main-default-view-issues-tab.png.png)

The default view for the Team Insights for Jira app is the Issues view.

You can switch to another view such as Epics, Teams or Backlog by clicking their specific tabs.

Use the search bar together with available search options to filter the list view.

The list view displays Jira issues showing priority, user activity, and other information:

| Column | Description |
|:-------|:------------|
| **_Name_** | The Name column shows the Jira issues that contain user and progress activities. |
| **_Priority_** | Displays the degree of priority of a Jira issue. |
| **_Status_** | Shows the progress status of a Jira issue. |
| **_Assignee_** | Shows the user the Jira issue is currently assigned to. |
| **_Contributor_** | Shows the contributor users actively worked on the Jira issue. |
| **_Sprint_** | Shows the sprint name a Jira issue is included in. |
| **_Days_** | Shows the number of days a Jira issue has been worked on. |
| **_Comments_** | Shows the number of comments a Jira issue has. |
| **_Commits_** | Shows the number of git commits a Jira issue has. |
| **_Pull requests_** | Shows the number of pull requests a Jira issue has. |

### Showing Issue Details

To view more details about a specific Jira issue, click on the twisty icon (**\>**) to expand it.

![](/wp-content/uploads/tij-gircloud-issue-view-item-details.png)

Click on the Issue details icon to display the detailed dialog of the Jira issue.

<img src='/wp-content/uploads/tij-gircloud-issue-view-issue-details-dialog.png' style='margin:25px auto;max-width:100%;display:block;' />

The issue details shows the following information on:

*   who the Jira issue is assigned to
*   which Jira issues the current ticket is waiting on
*   which Jira issues is causing the current ticket to stall
*   what is the current status of the Jira issue

### Sprints view

On the right section of the Issue list is the sprints view which displays the timeline of the sprint. This gives team managers the full picture of the progress of the Jira issues and what's the next step to do. They will also be able to see which Jira issues that needed attention and identify which team members are overloaded with tasks or which work is at risk for an upcoming due date.

![](/wp-content/uploads/tij-gitcloud-issues-view-timeline-labels.png)

The red line indicates today's date. If you drag the timeline scrubber, it changes the Activity date range filter. Hence, it will only show issues that have activity in that time frame. For example, dragging the slider to left lets you take a peek on what was worked on in the past few days or yesterday.

Hover the mouse pointer over the activity bar and it will show details about status changes, and statistics on development changes - for that day. This will display what type of work the team performed on that day.

<img src='/wp-content/uploads/tij-gitcloud-sissue-view-sprints-section-details.png' style='margin:25px auto;max-width:100%;display:block;' />

Click on the **Go to issue** shortcut to take you directly to that Jira issue.

Scroll the timeline horizontally by using the scrollbar at the bottom. The timeline shows a list of issues based on your selected Issue and Activity filters.

![](/wp-content/uploads/tij-gitcloud-issue-view-bottom-scroll-bar-loc.png)

Click on an Issue row to expand child issues and view additional information by moving the mouse pointer over the revealed icons.

![](/wp-content/uploads/tij-gitcloud-issue-view-timeline-row-details.png)

Finally, on the bottom part of the page, you will see the following shortcut controls:

| Control | Description |
|:--------|:------------|
| **_Displayed items_** | Set how many items per page will be displayed in the list view. |
| **_Page navigation_** | Shows the page controls to switch across several pages of information views. |
| **_Today_** | Clicking this button will automatically adjust the slider to today's date. |
| <img src='/wp-content/uploads/gij-question-mark-icon-32.png' style='height:16px;width:auto;' /> | Clicking this button will show quick helpful tips on how to navigate and use the Sprints, Epics or Teams view. |

### Epics View tab

![](/wp-content/uploads/tij-gitcloud-epics-view-main-screen.png)

The Epics View tab contains information that helps to organize the rows by epics. This allows team/product managers to easily expand and view the issues within each epic. While it functions closely similar to the Issues tab, it also provides an additional level of organization based on epics.

### Sorting in the Issues, and Epics View

Use the search and sort filters on the top part of the page to show only the data based on the selected criteria.

![](/wp-content/uploads/tij-gitcloud-backlog-view-search-panel.png)

Enter a text or word in the search box to find relevant issues and display it in the list view.

Utilize the search filters to narrow down what data to display in the list.

#### Sprints, active, future, backlog filter

![](/wp-content/uploads/tij-gitcloud-backlog-view-search-pane-typel.png)

Click on this filter to choose which type of issue to display. One or multiple types can be selected.

Utilize the **Find sprint** search box to identify which type the criteria belongs to. The counter will display how many hits are found for each type.

Click **Apply selection** to confirm and apply the selected types for search. Click **Clear** if you want to clear and reset the selection to default.

#### Activity filter

![](/wp-content/uploads/tij-gitcloud-backlog-view-search-pane-activity.png)

Click on this filter to choose interval on activity dates. The default filter is **All**.

Click on the choose interval dropdown to display available options. Choose **Custom** to set a specific date for the activity that you wanted to show.

Click **Clear** if you want to reset this filter to default.

#### Project filter

![](/wp-content/uploads/tij-gitcloud-backlog-view-search-pane-project.png)

Click on this filter and select the specific project you want to search in. Use the search box to narrow down your project list if you have multiple projects.

#### Assignee filter

For this filter, select one or more users to show only Jira issues that were assigned to the selected user(s). The default filter is **All**.

#### Clear All

Click this function to reset all search filter settings to default.

When you are finished setting up the filters, click **Search** to start the search.

### Sorting using the column headers

Click on the following column headers to toggle ascending or descending sorting of the list view by:

-   **Rank** -- This column displays the ranking of items in the list view.
-   **Issue Name** -- This column shows the name or title of each Jira issue.
-   **Priority** – This column indicates the priority level assigned to each Jira issue.
-   **Assignee Name** -- In this column, you can find the name of the person assigned to work on each Jira issue.
-   **Status** -- The status column represents the current state or progress of each Jira issue.

### More on Team Insights for Jira features

[Team Insights for Jira Cloud](/git-integration-for-jira-cloud/team-insights-for-jira-gij-cloud)

**Sprints/Epics View** (this page)

[Teams View](/git-integration-for-jira-cloud/team-insights-for-jira-teams-view-gij-cloud)

[Backlog View](/git-integration-for-jira-cloud/team-insights-for-jira-backlog-view-gij-cloud/)

[Pull request timeline reindex](/git-integration-for-jira-cloud/pull-request-timeline-for-tij-gij-cloud/)

