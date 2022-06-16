---

title: Proxy settings on adding integrations (except AWS CodeCommit)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

## Proxy settings for Jira

*   The client should specify **both** `http.proxyXXXX` and `https.proxyXXXX` parameters for Jira.

*   If the `Unable to tunnel through proxy. Proxy returns "HTTP/1.1 407 Proxy Authentication Required"` error occurs, then specify the options:

    *   `jdk.http.auth.tunneling.disabledSchemes=""`

    *   `jdk.http.auth.proxying.disabledSchemes=""`


## How to check if your connection uses a proxy

If you are unsure whether the connection goes through a proxy or directly you may use the following trick. Add the following rows in the /etc/hosts file to fool the direct routing:

```java
5.255.255.77 testgerrit.bigbrassband.tk -- for Gerrit
5.255.255.77 app.vssps.visualstudio.com -- for Microsoft
5.255.255.77 dev.azure.com -- for Microsoft
...
etc
```

If your connection uses a proxy, you will be able to connect to the chosen integration because all connections will be executed on the remote proxy server. Otherwise, all connections will be executed on your local machine where integration hosts will have incorrect host resolving issue.

