---

title: Javadocs example - Connect to a plain repository
description: Groovy ScriptRunner example that connects a private plain Git repository with a username and personal access token using GIJFacade.
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
tags: [scriptrunner, groovy, gijfacade, create repository, personal access tokens]
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.Repository;

String PRIVATE_ORIGIN = "https://yourhost/yourorganization/yourPrivateRepo.git";
String USERNAME = "yourUsername";
String PAT = "yourPATpIf6MNLQd4JqS09CnksaAe2Pnqy0hwCZD"

@PluginModule
GIJFacade gijFacade;

Repository newRepoParams = new Repository();
newRepoParams.setOrigin(PRIVATE_ORIGIN);
newRepoParams.setGitViewerEnabled(true);
newRepoParams.setUsername(USERNAME);
newRepoParams.setPat(PAT);

gijFacade.createRepository(newRepoParams);
```
