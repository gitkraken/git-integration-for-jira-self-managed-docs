---

title: Javadocs example - Connect to an integration
description: Groovy ScriptRunner example that creates a GitLab integration with a JMESPath API filter using GIJFacade.createIntegration.
product: Git Integration for Jira Data Center
feature: ScriptRunner
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [gitlab]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2022-08
llms_include: false
tags: [scriptrunner, groovy, gijfacade, create integration, jmespath]
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

IntegrationRequest newIntegration = new IntegrationRequest(IntegrationType.GITLAB, null, "yourPat", "My GitLab Integration");
newIntegration.setApiFilter("[?contains(name, 'test')]");
gijFacade.createIntegration(newIntegration);
```
