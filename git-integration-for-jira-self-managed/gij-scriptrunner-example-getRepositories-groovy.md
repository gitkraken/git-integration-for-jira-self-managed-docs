---

title: Javadocs example - gijFacade.getRepositories()
description: Groovy ScriptRunner example that lists all connected repositories using GIJFacade.getRepositories.
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
tags: [scriptrunner, groovy, gijfacade, repositories, list repositories]
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

gijFacade.getRepositories();
```
