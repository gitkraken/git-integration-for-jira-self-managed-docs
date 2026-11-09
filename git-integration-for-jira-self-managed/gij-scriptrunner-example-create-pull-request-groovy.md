---

title: Javadocs example - Create a new pull/merge request
description: Groovy ScriptRunner example that creates a pull or merge request linked to a Jira issue using GIJFacade.createPullRequest.
product: Git Integration for Jira Data Center
feature: ScriptRunner
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2022-08
llms_include: false
tags: [scriptrunner, groovy, gijfacade, create pull request, pull requests]
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.scriptrunner.models.PullRequest;


@PluginModule
GIJFacade gijFacade;

int REPO_ID = 2;
gijFacade.createPullRequest(REPO_ID, "TST-4-branch", "main", "Title - Test PR to be closed", "TST-4");
```
