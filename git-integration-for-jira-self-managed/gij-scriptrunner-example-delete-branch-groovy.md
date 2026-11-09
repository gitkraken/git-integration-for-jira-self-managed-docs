---

title: Javadocs example - Deleting a branch
description: Groovy ScriptRunner example that deletes a branch from a connected repository using GIJFacade.deleteBranch.
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
tags: [scriptrunner, groovy, gijfacade, delete branch, branches]
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;

@PluginModule
GIJFacade gijFacade;

int REPO_ID = 1;
gijFacade.deleteBranch(REPO_ID, "someBranch");
```
