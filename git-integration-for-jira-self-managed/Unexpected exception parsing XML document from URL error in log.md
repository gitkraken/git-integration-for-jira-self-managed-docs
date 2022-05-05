---

title: Unexpected exception parsing XML document from URL error in log
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Unexpected exception parsing XML document from URL error in log

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/732659727/Unexpected+exception+parsing+XML+document+from+URL+error+in+log>

* * *

## Problem

After Jira installation or configuration changes - the following errors appear. The Git Integration for Jira app may not enable.

## Diagnosis

Jira admins will see a message similar to the one below in the Jira log: `/application-logs/atlassian-jira.log` due to a plugin cache corruption.

|     |
| --- |
| **Error** |
| ```java<br>2020-06-18 11:26:38,203 ThreadPoolAsyncTaskExecutor::Thread 31 ERROR dwall 686x89952x1 11eu4cp 192.168.4.155 /rest/plugins/1.0/com.xiplink.jira.git.jira_git_plugin-key [o.e.g.b.e.i.dependencies.startup.DependencyWaiterApplicationContextExecutor] Unable to create application context for [com.xiplink.jira.git.jira_git_plugin], unsatisfied dependencies: none<br>org.springframework.beans.factory.BeanDefinitionStoreException: Unexpected exception parsing XML document from URL [bundle://280.0:0/META-INF/spring/atlassian-plugins-component-imports.xml]; nested exception is java.lang.IllegalStateException: The bundle is uninstalled.<br>at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:414)<br>at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:336)<br>at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:304)<br>at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:187)<br>at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:223)<br>at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:194)<br>at org.eclipse.gemini.blueprint.context.support.OsgiBundleXmlApplicationContext.loadBeanDefinitions(OsgiBundleXmlApplicationContext.java:171)<br>at org.eclipse.gemini.blueprint.context.support.OsgiBundleXmlApplicationContext.loadBeanDefinitions(OsgiBundleXmlApplicationContext.java:141)<br>at org.springframework.context.support.AbstractRefreshableApplicationContext.refreshBeanFactory(AbstractRefreshableApplicationContext.java:133)<br>at org.springframework.context.support.AbstractApplicationContext.obtainFreshBeanFactory(AbstractApplicationContext.java:619)<br>at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext.access$800(AbstractDelegatedExecutionApplicationContext.java:57)<br>at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext$3.run(AbstractDelegatedExecutionApplicationContext.java:239)<br>at org.eclipse.gemini.blueprint.util.internal.PrivilegedUtils.executeWithCustomTCCL(PrivilegedUtils.java:85)<br>at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext.startRefresh(AbstractDelegatedExecutionApplicationContext.java:217)<br>at org.eclipse.gemini.blueprint.extender.internal.dependencies.startup.DependencyWaiterApplicationContextExecutor.stageOne(DependencyWaiterApplicationContextExecutor.java:224)<br>at org.eclipse.gemini.blueprint.extender.internal.dependencies.startup.DependencyWaiterApplicationContextExecutor.refresh(DependencyWaiterApplicationContextExecutor.java:177)<br>at org.eclipse.gemini.blueprint.context.support.AbstractDelegatedExecutionApplicationContext.refresh(AbstractDelegatedExecutionApplicationContext.java:154)<br>at org.eclipse.gemini.blueprint.extender.internal.activator.LifecycleManager$1.run(LifecycleManager.java:213)<br>at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)<br>at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)<br>at java.lang.Thread.run(Thread.java:748)<br>Caused by: java.lang.IllegalStateException: The bundle is uninstalled.<br>at org.apache.felix.framework.Felix.getBundleResources(Felix.java:1706)<br>at org.apache.felix.framework.BundleImpl.getResources(BundleImpl.java:689)<br>at org.eclipse.gemini.blueprint.util.BundleDelegatingClassLoader.getResources(BundleDelegatingClassLoader.java:186)<br>at org.springframework.core.io.support.PropertiesLoaderUtils.loadAllProperties(PropertiesLoaderUtils.java:178)<br>at org.springframework.beans.factory.xml.DefaultNamespaceHandlerResolver.getHandlerMappings(DefaultNamespaceHandlerResolver.java:164)<br>at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins$Plugin.resolve(NamespacePlugins.java:77)<br>at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins$5.operate(NamespacePlugins.java:209)<br>at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins$5.operate(NamespacePlugins.java:205)<br>at org.eclipse.gemini.blueprint.extender.internal.support.LazyBundleRegistry.apply(LazyBundleRegistry.java:159)<br>at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins.doResolve(NamespacePlugins.java:205)<br>at org.eclipse.gemini.blueprint.extender.internal.support.NamespacePlugins.resolve(NamespacePlugins.java:169)<br>... 2 filtered<br>at java.lang.reflect.Method.invoke(Method.java:498)<br>at org.eclipse.gemini.blueprint.context.support.TrackingUtil$OsgiServiceHandler.invoke(TrackingUtil.java:106)<br>at com.sun.proxy.$Proxy614.resolve(Unknown Source)<br>at org.eclipse.gemini.blueprint.context.support.DelegatedNamespaceHandlerResolver.resolve(DelegatedNamespaceHandlerResolver.java:55)<br>at org.springframework.beans.factory.xml.BeanDefinitionParserDelegate.parseCustomElement(BeanDefinitionParserDelegate.java:1361)<br>at org.springframework.beans.factory.xml.BeanDefinitionParserDelegate.parseCustomElement(BeanDefinitionParserDelegate.java:1352)<br>at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:178)<br>at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.doRegisterBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:148)<br>at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.registerBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:98)<br>at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.registerBeanDefinitions(XmlBeanDefinitionReader.java:508)<br>at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:392)<br>... 20 more<br>``` |

## Cause

The Jira plugins cache might be corrupted. You may need to clear the plugins cache.

## Solution

1.  Stop Jira.
    
2.  Delete the following directories:
    
    1.  `JIRA_HOME/plugins/.bundled-plugins`
        
    2.  `JIRA_HOME/plugins/.osgi-plugins`
        
3.  Start Jira.
    

For more information - see this Atlassian Community article: [**UPM: Unexpected exception parsing XML document from URL**](https://community.atlassian.com/t5/Jira-Software-questions/UPM-Unexpected-exception-parsing-XML-document-from-URL/qaq-p/855850)

**Contact Us**  
If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com).

## Related articles

*   Page:
    
    [Why don't I see the Create Branch or Pull Request features?](/wiki/spaces/GIJDC/pages/123633735) (Git Integration for Jira Data Center)
    
*   Page:
    
    [TFS - Not authorized exception when Jira works thru proxy](/wiki/spaces/GIJDC/pages/128188471/TFS+-+Not+authorized+exception+when+Jira+works+thru+proxy) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Error while reindexing - Java heap space / Object too large, rejecting the pack](/wiki/spaces/GIJDC/pages/137035882) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Installation fails when installing manually](/wiki/spaces/GIJDC/pages/167247873/Installation+fails+when+installing+manually) (Git Integration for Jira Data Center)
    
*   Page:
    
    [SSH key file format is invalid](/wiki/spaces/GIJDC/pages/187957296/SSH+key+file+format+is+invalid) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Indexing error - Too many open files](/wiki/spaces/GIJDC/pages/318013497/Indexing+error+-+Too+many+open+files) (Git Integration for Jira Data Center)
    
*   Page:
    
    ["Service proxy has been destroyed" exceptions in log](/wiki/spaces/GIJDC/pages/458883074) (Git Integration for Jira Data Center)
    
*   Page:
    
    ["Dangerous use of multiple connections" error on local database](/wiki/spaces/GIJDC/pages/821919745) (Git Integration for Jira Data Center)
    
*   Page:
    
    [SQLException 'Incorrect string value' in merge requests](/wiki/spaces/GIJDC/pages/843448333/SQLException+%27Incorrect+string+value%27+in+merge+requests) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/wiki/spaces/GIJDC/pages/873332786/Avoid+OutOfMemory+exceptions+by+configuring+or+memory+allocation+with+Jira+to+accommodate+large+repositories) (Git Integration for Jira Data Center)