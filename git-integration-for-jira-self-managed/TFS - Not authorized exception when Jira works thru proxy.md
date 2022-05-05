---

title: TFS - Not authorized exception when Jira works thru proxy
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# TFS - Not authorized exception when Jira works thru proxy

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/128188471/TFS+-+Not+authorized+exception+when+Jira+works+thru+proxy>

* * *

## Problem

Technical error reported from the git client:

```java
org.eclipse.jgit.errors.TransportException
http://127.0.0.1:8080/tfs/DefaultCollection/_git/console-app/: not authorized
```

Attempt to connect to the Git server failed. This may be because of invalid username and password or may be because of a network error.

  

## Diagnosis

The above error is similar to _**"service=git-upload pack not found"**_ type errors and happens when the credentials being used by the Git Integration app don't have access to clone the specified Git repositories. There's the possibility to see the repositories from the TFS API (they are actually listed) but unable to access them via the Git protocol.

  

## Solution

If you are using proxy, configure your Jira with the following parameter format:

```py
Dhttp.proxyHost=<your-proxy-host>
Dhttps.proxyHost=<your-proxy-host>
Dhttp.proxyPort=<your-proxy-port>
Dhttps.proxyPort=<your-proxy-port>
Dhttp.proxyUser=*****
Dhttps.proxyUser=*****
Dhttp.proxyPassword=*****
Dhttps.proxyPassword=*****
Dhttp.nonProxyHosts=*.some.mask|localhost|1.1.1.1<someIP>
Dhttps.nonProxyHosts=*.some.mask|localhost|1.1.1.1<someIP>
```

Enter**`<your-git-server-host>`**to**`nonProxyHosts`**entries.

Usually, the **nonProxyHosts** are the list of servers that the JVM should **not** send through the proxy. This is because they are in the same data center and a private address.

Wildcards are supported:

```java
-Dhttp.nonProxyHosts=*.git.server.host
-Dhttps.nonProxyHosts=*.git.server.host
```

Or instead, use pipe and quotes for multiple hosts:

```java
-Dhttp.nonProxyHosts="your.git.server.host1|your.git.server.host2"
-Dhttps.nonProxyHosts="your.git.server.host1|your.git.server.host2"
```