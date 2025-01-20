---

title: Team Insights for Jira Data Center
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/tij-datacenter-issues-view-start.png)

The Team Insights for Jira DC extension equips team managers with the tools to effectively track comprehensive git history and monitor Jira team activities across various projects, epics, and sprints. This functionality allows team leaders to efficiently prioritize tasks, identify potential risks, reveal patterns, and enhance decision-making when overseeing Jira team workflows and activities.

Team Insights for Jira (TIJ) provides team managers with a comprehensive overview of their team's activities and progress. This allows managers to pinpoint any items that may be at risk based on the team's operation.

&nbsp;

### Compatibility

![](/wp-content/uploads/tij-datacenter-marketplace-listing-view.png)

The Team Insights for Jira DC extension version 1.3.4 officially supports Jira Data Center versions **8.5.5** up to **9.17.2**.

Team Insights for Jira DC is scheduled to be released for Jira 10 instances soon.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you have <a href='https://marketplace.atlassian.com/apps/4984/git-integration-for-jira-azure-devops-github-gitlab?tab=overview&hosting=datacenter'>Git Integration for Jira Data Center app</a> installed, it can enhance your planning workflow and provide more information by integrating Git data into your views.
    </div>
    </div>
</div>

&nbsp;

### Permissions to see TIJ data

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b>

Viewing Team Insights for Jira data is derived from the Jira user permissions they are assigned with. Therefore, if users have access to Jira issues, they will also be able to view TIJ data.

&nbsp;

### Installation

Go to the Atlassian Marketplace, then search for "**Team Insights for Jira**". If search returns no results, then your Jira instance version is not supported.

![](/wp-content/uploads/tij-datacenter-installation-marketplace.png)

Click **Install**. The following dialog is displayed.

![](/wp-content/uploads/tij-datacenter-installation-accept-and-install.png)

Click **Accept & install** to start the installation.

When the installation is complete, the following dialog is displayed. Click **Close** to start using Team Insights for Jira.

![](/wp-content/uploads/tij-datacenter-installation-ready.png)

Two new app items are added to the Manage apps list, namely, **Team Insights for Jira** and **Sprint History**.

![](/wp-content/uploads/tij-datacenter-manage-apps-installed-apps.png)

&nbsp;

### Feature matrix

With Team Insights for Jira DC app, team managers will be able to see team activity across projects, epics and sprints.

| Feature   | TIJ Only  | GIJ + TIJ |
|:----------|:----------|:----------|
| Identify stale issues or issues that revert in status | ![](/wp-content/uploads/gij-matrix-open-check-green.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| See activities for sprint planning, stand ups, and retrospectives<sup>1</sup> | ![](/wp-content/uploads/gij-matrix-open-check-green.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Helpful insights for executives, managers, and individual contributors<sup>1</sup> | ![](/wp-content/uploads/gij-matrix-open-check-green.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Enables all team members to identify and contribute improvements | ![](/wp-content/uploads/gij-matrix-open-check-green.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Valuable for all departments that use Jira in your organization | ![](/wp-content/uploads/gij-matrix-open-check-green.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Easily see issues status progress over time, where it changed and how long it remained in that state | ![](/wp-content/uploads/gij-matrix-open-check-green.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Identify pull requests that remain open for too long<sup>2</sup> | ![](/wp-content/uploads/gij-matrix-open-not-red.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| View commits and other git related data for your team. | ![](/wp-content/uploads/gij-matrix-open-not-red.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Create branches and pull/merge requests in Jira issues for your team | ![](/wp-content/uploads/gij-matrix-open-not-red.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Link webhooks to your Git and Jira for faster display of git data | ![](/wp-content/uploads/gij-matrix-open-not-red.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Manage git integrations and repository connections | ![](/wp-content/uploads/gij-matrix-open-not-red.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |
| Assign other users to manage integrations and repository connections | ![](/wp-content/uploads/gij-matrix-open-not-red.png) | ![](/wp-content/uploads/gij-matrix-open-check-green.png) |

<b><sup>1</sup></b> With Git Integration for Jira app also installed, git data is displayed in a more detailed manner

<b><sup>2</sup></b> Requires Git Integration for Jira app installed if you want to see pull request status and information.

&nbsp;

### App access location

Once you have successfully installed the application, you will be able to access Team Insights for Jira via the Jira dashboard menu. Simply navigate to Jira dashboard then click the **Insights** tab.

![](/wp-content/uploads/tij-datacenter-menu-access-location.png)

&nbsp;

### Features and highlights

Team Insights for Jira DC provides you with the ability to view Git activity across all of your projects and issues. These features offer useful insights into your team's collaboration and development processes. And best of all, it's completely free!

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        By analyzing the Git activity, you can identify trends, track progress, and make data-driven decisions to improve productivity and efficiency.
    </div>
    </div>
</div>

#### Customize Your View Across Projects, Epics, and Issues

Team Insights for Jira DC aims to improve your workflows and provide you with the data you need to put you on the right direction. View the timeline by Epics, Issues and Sub-tasks and filter by project, sprint, team members, issue status, and more. Manage tasks by sorting them based on criteria. For example, you can sort tasks by the number of days since the last status update or by the number of commits made.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        By utilizing these sorting options, you can monitor and prioritize your team’s workflow and stay organized.
    </div>
    </div>
</div>

#### Manage Jira Workflows Efficiently

Focus on the Jira issues that demand immediate attention:

*   Gain insight into actions performed by users and their timing across multiple Jira issues.
*   Determine tasks easily that are at risk of missing upcoming deadlines.
*   Identify team members that have an excessive workload in a more detailed view.
*   Pinpoint stagnant problems, reverted closed issues, and pull requests that remain open for an extended period of time.

#### Enhance Team Collaboration with TIJ Views

Enable every team member and all departments to enhance their understanding by utilizing TIJ views during sprints and epics planning. When analyzing data, individuals can identify recurring patterns, detect trends, and uncover potential areas for improvement. This process helps them understand the entire progress ahead of time.

#### Track and Improve Team Productivity

Team Insights for Jira provides a comprehensive view of your team's Jira and Git activity over time. It allows you to easily track what tasks your team is currently working on and monitor their progress, thus impacting on productivity and efficiency.

TIJ displays Jira activity for all Jira users. Git data such as branches, commits, pull requests, and tags are automatically included in the views if you have the [Git Integration for Jira DC app](https://www.gitkraken.com/git-integration-for-jira) installed.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This combination is ideal for team workflows and git integration without requiring any additional setup or configuration.
    </div>
    </div>
</div>

&nbsp;

### More on Team Insights for Jira Data Center features

**Main TIJ page** (this page)

[Issues View](/git-integration-for-jira-data-center/Team-insights-for-jira-datacenter-issues-view-gij-self-managed)

_Epics View (Coming soon)_

[Pull request timeline for Team Insights for Jira DC](/git-integration-for-jira-data-center/Team-insights-for-jira-datacenter-pullreq-timeline-gij-self-managed)

