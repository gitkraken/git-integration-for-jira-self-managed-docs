---

title: Javadocs example - Create/delete/reindex a repository
description: "Groovy ScriptRunner example that connects a repository, runs a synchronous reindex and optionally deletes it using GIJFacade."
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
tags: [scriptrunner, groovy, gijfacade, create repository, delete repository, reindex]
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

String SMALL_PUBLIC_REPO_HTTP_ORIGIN = "https://github.com/githubtraining/hellogitworld.git";

@PluginModule
GIJFacade gijFacade;

Repository newRepoParams = new Repository();
newRepoParams.setOrigin(SMALL_PUBLIC_REPO_HTTP_ORIGIN);
newRepoParams.setGitViewerEnabled(true);

Integer newRepoId = null;

try {
    newRepoParams = gijFacade.createRepository(newRepoParams);
    newRepoId = newRepoParams.getId();
    log.error("new repo id = " + newRepoId);

    boolean isSuccessful = gijFacade.doReindexSynchronized(newRepoId);
    log.error("reindex has finished. isSuccessful = " + isSuccessful);
} finally {
    if (newRepoId != null) {
        //gijFacade.deleteRepository(newRepoId, true); // uncomment the code to delete the repository at the end
    }
}
```
