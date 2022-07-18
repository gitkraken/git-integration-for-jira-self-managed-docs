# Example of create/delete/reindex of repository

```
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
