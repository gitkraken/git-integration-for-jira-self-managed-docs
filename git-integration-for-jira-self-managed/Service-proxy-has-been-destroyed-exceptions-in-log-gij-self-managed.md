---

title: Service proxy has been destroyed exceptions in log
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## Problem

Errors/failures in the Git Integration for Jira application are seen sporadically.

## Diagnosis

Jira admins will see a message similar to the one below in the Jira log -- `/application-logs/atlassian-jira.log`:

**Error**
```java
2019-07-07 07:07:072,777 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 0 ERROR      [c.b.j.g.s.indexer.revisions.RevisionIndexerImpl] Unable to index repository 'my-repository-example-name' (repoId: 777)
org.eclipse.gemini.blueprint.service.importer.ServiceProxyDestroyedException: service proxy has been destroyed
    at org.eclipse.gemini.blueprint.service.importer.support.internal.aop.ServiceDynamicInterceptor$ServiceLookUpCallback.doWithRetry(ServiceDynamicInterceptor.java:101)
    at org.eclipse.gemini.blueprint.service.importer.support.internal.support.RetryTemplate.execute(RetryTemplate.java:81)
    at org.eclipse.gemini.blueprint.service.importer.support.internal.aop.ServiceDynamicInterceptor.lookupService(ServiceDynamicInterceptor.java:427)
    at org.eclipse.gemini.blueprint.service.importer.support.internal.aop.ServiceDynamicInterceptor.getTarget(ServiceDynamicInterceptor.java:400)
    at org.eclipse.gemini.blueprint.service.importer.support.internal.aop.ServiceInvoker.invoke(ServiceInvoker.java:60)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)
    at org.springframework.aop.support.DelegatingIntroductionInterceptor.doProceed(DelegatingIntroductionInterceptor.java:136)
    at org.springframework.aop.support.DelegatingIntroductionInterceptor.invoke(DelegatingIntroductionInterceptor.java:124)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)
    at org.eclipse.gemini.blueprint.service.util.internal.aop.ServiceTCCLInterceptor.invokeUnprivileged(ServiceTCCLInterceptor.java:70)
    at org.eclipse.gemini.blueprint.service.util.internal.aop.ServiceTCCLInterceptor.invoke(ServiceTCCLInterceptor.java:53)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)
    at org.eclipse.gemini.blueprint.service.importer.support.LocalBundleContextAdvice.invoke(LocalBundleContextAdvice.java:57)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)
    at org.springframework.aop.support.DelegatingIntroductionInterceptor.doProceed(DelegatingIntroductionInterceptor.java:136)
    at org.springframework.aop.support.DelegatingIntroductionInterceptor.invoke(DelegatingIntroductionInterceptor.java:124)
    at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185)
    at org.springframework.aop.framework.JdkDynamicAopProxy.invoke(JdkDynamicAopProxy.java:212)
    at com.sun.proxy.$Proxy2505.getAllTranslationsForPrefix(Unknown Source)
    at com.bigbrassband.jira.git.utils.I18nManager.getForPrefix(I18nManager.java:54)
    at com.bigbrassband.jira.git.utils.I18nManager.getText(I18nManager.java:62)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.handleUpdateError(GitPluginIndexManagerImpl.java:303)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.fetchImpl(GitPluginIndexManagerImpl.java:523)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.callFetch(GitPluginIndexManagerImpl.java:502)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.updateIndex(GitPluginIndexManagerImpl.java:339)
    at com.bigbrassband.jira.git.services.indexer.revisions.RevisionIndexerImpl$1.doRun(RevisionIndexerImpl.java:151)
    at com.bigbrassband.jira.git.services.indexer.revisions.QueueEntry.run(QueueEntry.java:82)
    at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
    at java.util.concurrent.FutureTask.run(FutureTask.java:266)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
```

## Cause

On occasion - the Atlassian Universal Plugin Manager (UPM) will not stop threads from previous versions of the Git Integration for Jira plugin.

## Solution

No configuration or source code data is lost when uninstalling, disabling or cleaning up plugin folders. However - if you wish to export your settings prior to these change - use the [Bulk Change export](/git-integration-for-jira-data-center/bulk-export-gij-self-managed).

**Update the** [**Atlassian Universal Plugin Manager**](https://marketplace.atlassian.com/apps/23915/atlassian-universal-plugin-manager) **("UPM") to the latest version prior to using the following solutions:**

### Step 1: Re-enable app.

1.  Disable the _Git Integration for Jira_ app in **Manage apps**.

2.  Re-enable _Git Integration for Jira_ app.

3.  _Optional:_ Restart Jira.

4.  Reindex repositories.

5.  If symptoms persist, proceed to next step.

### Step 2: Reinstall app.

1.  Update the Universal Plugin Manager (UPM) to the [**latest version**](https://marketplace.atlassian.com/apps/23915/atlassian-universal-plugin-manager?tab=versions) offered by Atlassian.

2.  Uninstall the _Git Integration for Jira_ app in **Manage apps**.

3.  Re-install _Git Integration for Jira_ app.

4.  _Optional:_ Restart Jira.

5.  Reindex repositories.

6.  If symptoms persist, proceed to next step.

### Step 3: Clean up plugin folders.

1.  Stop Jira.

2.  Clean up [**plugin temp folders**](https://answers.atlassian.com/questions/7110972/can-we-clean-up-osgi-plugins-in-jira) fully or remove these files:

    *   `JIRA_INSTALL_FOLDER/temp/*_git_plugin-*.jar`

    *   `JIRA_HOME_FOLDER/plugins/.osgi-plugins/transformed-plugins/*_git_plugin-*.jar`

3.  Remove all versions of the **Git Integration for Jira** app from the `installed-plugins` folder except the [**latest version**](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions):

    *   `JIRA_HOME_FOLDER/plugins/installed-plugins/*_git_plugin-*.jar`

4.  Start Jira.

5.  Reindex repositories.

6.  If symptoms persist, contact BigBrassBand Support.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>
<br>

