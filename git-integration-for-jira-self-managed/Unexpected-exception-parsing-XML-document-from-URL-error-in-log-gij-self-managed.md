---

title: Unexpected exception parsing XML document from URL error in log
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Problem

After Jira installation or configuration changes - the following errors appear. The Git Integration for Jira app may not enable.

## Diagnosis

Jira admins will see a message similar to the one below in the Jira log: `/application-logs/atlassian-jira.log` due to a plugin cache corruption.


**Error**

```java
2020-06-18 11:26:38,203 ThreadPoolAsyncTaskExecutor::Thread 31 ERROR dwall 686x89952x1 11eu4cp 192.168.4.155 /rest/plugins/1.0/com.xiplink.jira.git.jira_git_plugin-key [o.e.g.b.e.i.dependencies.startup.DependencyWaiterApplicationContextExecutor] Unable to create application context for [com.xiplink.jira.git.jira_git_plugin], unsatisfied dependencies: none
org.springframework.beans.factory.BeanDefinitionStoreException: Unexpected exception parsing XML document from URL [bundle://280.0:0/META-INF/spring/atlassian-plugins-component-imports.xml]; nested exception is java.lang.IllegalStateException: The bundle is uninstalled.
at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:414)
at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:336)
at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:304)
at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:187)
at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:223)
at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:194)
at org.eclipse.gemini.blueprint.context.support.OsgiBundleXmlApplicationContext.loadBeanDefinitions(OsgiBundleXmlApplicationContext.java:171)
at org.eclipse.gemini.blueprint.context.support.OsgiBundleXmlApplicationContext.loadBeanDefinitions(OsgiBundleXmlApplicationContext.java:141)
at org.springframework.context.support.AbstractRefreshableApplicationContext.refreshBeanFactory(AbstractRefreshableApplicationContext.java:133)
at org.springframework.context.support.AbstractApplicationContext.obtainFreshBeanFactory(AbstractApplicationContext.java:619)
at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext.access$800(AbstractDelegatedExecutionApplicationContext.java:57)
at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext$3.run(AbstractDelegatedExecutionApplicationContext.java:239)
at org.eclipse.gemini.blueprint.util.internal.PrivilegedUtils.executeWithCustomTCCL(PrivilegedUtils.java:85)
at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext.startRefresh(AbstractDelegatedExecutionApplicationContext.java:217)
at org.eclipse.gemini.blueprint.extender.internal.dependencies.startup.DependencyWaiterApplicationContextExecutor.stageOne(DependencyWaiterApplicationContextExecutor.java:224)
at org.eclipse.gemini.blueprint.extender.internal.dependencies.startup.DependencyWaiterApplicationContextExecutor.refresh(DependencyWaiterApplicationContextExecutor.java:177)
at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext.refresh(AbstractDelegatedExecutionApplicationContext.java:154)
at org.eclipse.gemini.blueprint.extender.internal.activator.LifecycleManager$1.run(LifecycleManager.java:213)
at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
at java.lang.Thread.run(Thread.java:748)
Caused by: java.lang.IllegalStateException: The bundle is uninstalled.
at org.apache.felix.framework.Felix.getBundleResources(Felix.java:1706)
at org.apache.felix.framework.BundleImpl.getResources(BundleImpl.java:689)
at org.eclipse.gemini.blueprint.util.BundleDelegatingClassLoader.getResources(BundleDelegatingClassLoader.java:186)
at org.springframework.core.io.support.PropertiesLoaderUtils.loadAllProperties(PropertiesLoaderUtils.java:178)
at org.springframework.beans.factory.xml.DefaultNamespaceHandlerResolver.getHandlerMappings(DefaultNamespaceHandlerResolver.java:164)
at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins$Plugin.resolve(NamespacePlugins.java:77)
at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins$5.operate(NamespacePlugins.java:209)
at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins$5.operate(NamespacePlugins.java:205)
at org.eclipse.gemini.blueprint.extender.internal.support.LazyBundleRegistry.apply(LazyBundleRegistry.java:159)
at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins.doResolve(NamespacePlugins.java:205)
at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins.resolve(NamespacePlugins.java:169)
... 2 filtered
at java.lang.reflect.Method.invoke(Method.java:498)
at org.eclipse.gemini.blueprint.context.support.TrackingUtil$OsgiServiceHandler.invoke(TrackingUtil.java:106)
at com.sun.proxy.$Proxy614.resolve(Unknown Source)
at org.eclipse.gemini.blueprint.context.support.DelegatedNamespaceHandlerResolver.resolve(DelegatedNamespaceHandlerResolver.java:55)
at org.springframework.beans.factory.xml.BeanDefinitionParserDelegate.parseCustomElement(BeanDefinitionParserDelegate.java:1361)
at org.springframework.beans.factory.xml.BeanDefinitionParserDelegate.parseCustomElement(BeanDefinitionParserDelegate.java:1352)
at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:178)
at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.doRegisterBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:148)
at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.registerBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:98)
at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.registerBeanDefinitions(XmlBeanDefinitionReader.java:508)
at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:392)
... 20 more
```

## Cause

The Jira plugins cache might be corrupted. You may need to clear the plugins cache.

## Solution

1.  Stop Jira.

2.  Delete the following directories:

    *   `JIRA_HOME/plugins/.bundled-plugins`

    *   `JIRA_HOME/plugins/.osgi-plugins`

3.  Start Jira.

<br>

For more information - see this Atlassian Community article: [UPM: Unexpected exception parsing XML document from URL](https://community.atlassian.com/t5/Jira-Software-questions/UPM-Unexpected-exception-parsing-XML-document-from-URL/qaq-p/855850)

<br>

<div class="bbb-callout bbb--info">
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

<br>

## More articles about troubleshooting, workarounds and solutions

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/Avoid-OutOfMemory-exceptions-by-configuring-or-memory-allocation-with-Jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

[Duplicate entry 0 for key PRIMARY exceptions in log](/git-integration-for-jira-data-center/Duplicate-entry-0-for-key-PRIMARY-exceptions-in-log-gij-self-managed)

[Error while reindexing - Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Gitolite integration: Why the Git integration app not see the master branch?](/git-integration-for-jira-data-center/Gitolite-integration--why-the-Git-integration-app-not-see-the-master-branch-gij-self-managed)

[Health Check\: Database Collation](/git-integration-for-jira-data-center/Health-check--database-collation-gij-self-managed)

[Indexing error - Too many open files](/git-integration-for-jira-data-center/Indexing-error-Too-many-open-files-gij-self-managed)

[Installation fails when installing manually](/git-integration-for-jira-data-center/Installation-fails-when-installing-manually-gij-self-managed)

[Jira index error: IndexNotFoundException: no segments\* file found](/git-integration-for-jira-data-center/Jira-index-error--IndexNotFoundException--no-segments-file-found)

[Malformed input or input contains unmappable characters](/git-integration-for-jira-data-center/Malformed-input-or-input-contains-unmappable-characters-gij-self-managed)

[Personal access token failing Azure DevOps integration with Not Authorized error](/git-integration-for-jira-data-center/Personal-access-token-failing-azure-devops-integration-with-Not-Authorized-error-gij-self-managed)

[Problems with shared home on Azure Storage](/git-integration-for-jira-data-center/Problems-with-shared-home-on-azure-storage-gij-self-managed)

[Pull request index error: org.json.JSONException](/git-integration-for-jira-data-center/Pull-request-index-error--JSONException-gij-self-managed)

[Repositories missing from Azure DevOps integration](/git-integration-for-jira-data-center/Repositories-missing-from-azure-devops-integration-gij-self-managed)

[Service proxy has been destroyed  exceptions in log](/git-integration-for-jira-data-center/Service-proxy-has-been-destroyed-exceptions-in-log-gij-self-managed)

[SQLException Incorrect string value in merge requests](/git-integration-for-jira-data-center/SQLException-'Incorrect-string-value'-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/SSH-key-file-format-is-invalid-gij-self-managed)

[TFS - Not Authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/TFS-Not-authorized-exception-when-Jira-works-thru-proxy-gij-self-managed)

**Unexpected exception parsing XML document from URL error in log** (this page)

