---

title: Issue Git integration panel
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

**Note**
By default, [Git Integration for Jira](https://marketplace.atlassian.com/4984) has the Git integration panel enabled. (How to disable)

The **View developer tools** _permission_ is required to view the Issue Git integration panel. Jira users must also have the **Browse Project** _permissions_ to a project associated with a repository to view.

## Overview

The Issue Git integration panel displays:

*   **Git Commits:** number of commits and link to [Git Commits Issue Tab](#), link to [Git Roll Up Issue Tab](#).

*   **Branches:** Create branch function, list of branches associated to Jira issue (Jira issue key must be in branch title)

*   **Pull/Merge Requests:** Create pull/merge request function, list of pull/merge requests associated to Jira issue (Jira issue key must be in PR/MR title), status of pull/merge request

*   **Tags:** git tags associated to Jira issue (via associated commit). Tags are sometimes referred to as Releases in some products.


![](https://bigbrassband.atlassian.net/wiki/download/attachments/1932329305/gitserver-git-integration-panel-view.png?version=1&modificationDate=1642594991246&cacheVersion=1&api=v2)

## How can a Jira administrator enable or disable the Issue Git integration development panel?

1.  Install the [Git Integration for Jira](https://marketplace.atlassian.com/4984) app.

2.  Navigate to the [**General settings**](/git-integration-for-jira-self-managed/General-Settings) page of the application.

3.  Enable or disable the setting: `Show Git integration panel on issue pages`.

4.  Click **Update** button.


![](https://bigbrassband.atlassian.net/wiki/download/attachments/1932329305/gitserver-gencfg-dev-panel-sel.png?version=1&modificationDate=1642598628491&cacheVersion=1&api=v2)

**Contact us**
If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com)

### More articles on features

*   Page:

    [Smart commits overview](/wiki/spaces/GIJDC/pages/109215851/Smart+commits+overview)

*   Page:

    [Associate Pull/Merge Requests to Issues Based on Commits](/wiki/spaces/GIJDC/pages/966852625)

*   Page:

    [General Settings](/git-integration-for-jira-self-managed/General-Settings)

*   Page:

    [Creating branches](/git-integration-for-jira-self-managed/Creating-branches)

*   Page:

    [Creating pull/merge requests](/wiki/spaces/GIJDC/pages/1932460359)

*   Page:

    [Issue Git integration panel](/wiki/spaces/GIJDC/pages/1932329305/Issue+Git+integration+panel)

*   Page:

    [Deep Linking to the GitKraken Git client](/wiki/spaces/GIJDC/pages/1955430423/Deep+Linking+to+the+GitKraken+Git+client)

*   Page:

    [Enforced git permissions for Jira users](/wiki/spaces/GIJDC/pages/2091810817/Enforced+git+permissions+for+Jira+users)