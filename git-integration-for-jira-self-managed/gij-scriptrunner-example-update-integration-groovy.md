---

title: Javadocs example - Updating an integration
description: Groovy ScriptRunner example that renames an existing integration using GIJFacade.updateIntegration.
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
tags: [scriptrunner, groovy, gijfacade, update integration, integrations]
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.integration.IntegrationType;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.integration.IntegrationRequest;


@PluginModule
GIJFacade gijFacade;

int REPO_ID = 26;
IntegrationRequest newIntegration = new IntegrationRequest();
newIntegration.setDisplayName("new name gitlab");
gijFacade.updateIntegration(REOP_ID, newIntegration);
```
