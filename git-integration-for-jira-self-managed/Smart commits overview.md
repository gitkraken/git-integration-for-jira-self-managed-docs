---

title: Smart commits overview
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---



Git Integration for Jira. See Git commits in Jira.

## **Introduction**

Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

The Git Integration for Jira app, the smart commit processing is **active by default** and can be enabled/disabled via the repository configuration:

![](https://bigbrassband.com/docimgs/smart-commit-setting.png)

Smart commits configuration checklist:

*   The Jira DVCS Connector Plugin is not required.
*   Your Jira e-mail address and Git commit e-mail address matches.
*   E-mail address is not shared by other Jira users.

The basic syntax for a smart commit message is:

<ISSUE\_KEY> 

_<ignored text>_ 

#<command> 

_<optional command\_params>_





For more information on the Smart Commits feature, see [Documentation: Smart commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits).



* * *



## **Did You Know?**





Jira User

The committers’ email address in the git configuration must match with the email address of the corresponding Jira user (or vice versa) for the smart commit to work.



Project Permissions

The Jira user must have the appropriate project permissions to transition issues.



Workflow Transition

When you hover a status on the Issue Workflow - it will highlight available transitions.  This is the transition name that is used in Smart Commits.



Email Notifications

If a smart commit fails, an email notification is sent to either the Jira user, or to the Git user if a Jira user cannot be identified.



Transition Names

To avoid conflict when transitioning issues, give a unique name to a workflow transition.



Smart Commit Helper

When the **Smart Commits** setting is disabled for that repository, the Git Integration for Jira app will not show the [COMMIT indicators](/wiki/spaces/GIJDC/pages/1930398529/Smart+commits+helper).



Multi-line Commits

v2.6.33+ The Git Integration for Jira app, support for multi-line commit messages for Smart Commits has been implemented.

[Related topic »](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398446/Advanced+examples#multi-line)



Smart Commit Status

The commit status shown on the Issue page depends on the Smart Commits setting that was set at the time the commits were processed.

Need to know more?  Read further at  [Documentation: Smart commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits).

## More articles on features

*   Page:

    [Smart commits overview](/wiki/spaces/GIJDC/pages/109215851/Smart+commits+overview)

*   Page:

    [Associate Pull/Merge Requests to Issues Based on Commits](/wiki/spaces/GIJDC/pages/966852625)

*   Page:

    [General Settings](/wiki/spaces/GIJDC/pages/966852655/General+Settings)

*   Page:

    [Creating branches](/wiki/spaces/GIJDC/pages/1932460323/Creating+branches)

*   Page:

    [Creating pull/merge requests](/wiki/spaces/GIJDC/pages/1932460359)

*   Page:

    [Issue Git integration panel](/wiki/spaces/GIJDC/pages/1932329305/Issue+Git+integration+panel)

*   Page:

    [Deep Linking to the GitKraken Git client](/wiki/spaces/GIJDC/pages/1955430423/Deep+Linking+to+the+GitKraken+Git+client)

*   Page:

    [Enforced git permissions for Jira users](/wiki/spaces/GIJDC/pages/2091810817/Enforced+git+permissions+for+Jira+users)