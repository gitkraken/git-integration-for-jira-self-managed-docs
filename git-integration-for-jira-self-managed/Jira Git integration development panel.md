---

title: Jira Git integration development panel
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This page applies to Git Integration for Jira Server and Jira Data Center.

## Permissions

|     |
| --- |
| **Jira Cloud - Development panel** |
| The **View Development Tools** _permission_ only applies to Jira Classic Projects. Next-Gen Projects don't allow to modify the permission. |
| **Create Branches and Branch Names** |
| For connected GitHub git host, this feature requires enabled `public_repo` scope permissions. |
| **Commits Ahead and Behind** |
| If the user does not have the **View Development Tools** _project permission_ for the project, the developer panel will be unavailable for that user. |

## Getting started

Git links are now available on the developer panel in the following locations:

*   Issue page

*   Search page in detailed view

*   Jira Agile screen


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399012/new-jira-developer-panel.png?version=1&modificationDate=1630642916834&cacheVersion=1&api=v2&width=210&height=430)

The **30 commits** refers to an existing Git Commits view, which the issue tab have now. Clicking this text link will reload the page and automatically switches to the **Git Commits** tab to view the commits.

The **Roll Up** refers to an existing Git Roll Up view, which the issue tab have now. Clicking this link will reload the page and automatically switches to the **Git Roll Up** tab to view the git code summary.

|     |
| --- |
| Click **Compare code** to open the following dialog: |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399012/dev-panel-compare-code-dlg.png?version=1&modificationDate=1630642917074&cacheVersion=1&api=v2&width=544&height=285)<br><br>  <br>Compare code diff of different branches by performing the following options:<br><br>1.  Select a **Repository**.<br>    <br>2.  Set **Compare** branch and **Base** branch.<br>    <br>3.  Click **Compare** to proceed.<br>    <br><br>The view redirects to the Repository Browser ➜ **Compare** tab showing changes between the compared branches.<br><br>The most commonly used name for the main branch is _**master**_. For this documentation, the _**master**_ branch is also the main branch. |

[« Jira issue page](/wiki/spaces/GIJDC/pages/1930398870/Jira+issue+page)

[Development panel locations »](/wiki/spaces/GIJDC/pages/1930399041/Development+panel+locations)

