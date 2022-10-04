---

title: Cannot auto-deploy some tracked repositories -- Specified origin is incorrect or not supported
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## Problem

Git Integration for Jira application is not able to index repositories from a self-hosted GitLab or GitHub server.

## Diagnosis

List of repositories may load in the wizard correctly - but repositories are not indexed.
Logs contain a message similar to:

```java
Сan't auto-deploy a new repository http://gitlab-server.company.com/path/repository.git
com.bigbrassband.jira.git.exceptions.InvalidRemoteOperationException: Specified origin http://gitlab-server.company.com/path/repository.git is incorrect or not supported
```

## Cause

GitLab or GitHub permissions of the service user connecting Jira (via the Git Integration for Jira app) are not sufficient to view source code for the repository.

## Solutions

Grant sufficient access to the service account user in GitLab or GitHub:

*   See [GitLab permissions](https://docs.gitlab.com/ee/user/permissions.html) (Reporter is minimum required)

*   See [GitHub permissions](https://help.github.com/en/articles/access-permissions-on-github#personal-user-accounts) (Read for GitHub organizations or Collaborator for personal owned repositories is is minimum required).

<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='gijsupport@bigbrassband.com'>gijsupport@bigbrassband.com</a>.
    </div>
    </div>
</div>
<br>

