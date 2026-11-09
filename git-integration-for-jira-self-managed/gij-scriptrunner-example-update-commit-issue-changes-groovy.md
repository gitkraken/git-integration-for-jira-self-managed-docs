---

title: Javadocs example - Update commmit issues associations
description: Groovy ScriptRunner example that updates which Jira issues a commit is linked to using GIJFacade.updateCommitIssueChanges.
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
tags: [scriptrunner, groovy, gijfacade, commit issue association, linking commits]
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.IssuesAssociationRequest;

@PluginModule
GIJFacade gijFacade;

int REPO_ID = 1;
gijFacade.updateCommitIssueChanges(REPO_ID, "ec43e12cda0fa4f021d4dead8eadb8781efbb4b0", new IssuesAssociationRequest().addLink("TST-6"));
```
