---

title: Javadocs example - Start sync reindex of a repository
description: Groovy ScriptRunner example that runs a synchronous reindex of a repository using GIJFacade.doReindexSynchronized.
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
tags: [scriptrunner, groovy, gijfacade, reindex, synchronous reindex]
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.IndexStatusResponse;

@PluginModule
GIJFacade gijFacade;

int REPO_ID = 1;
gijFacade.doReindexSynchronized(REPO_ID);
```
