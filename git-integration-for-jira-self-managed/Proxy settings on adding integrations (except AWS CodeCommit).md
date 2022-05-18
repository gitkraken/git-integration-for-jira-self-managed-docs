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

## More how-to articles

*   Page:

    [Creating Personal Access Tokens](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens)

*   Page:

    [Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters)

*   Page:

    [Working with Custom API Path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path)

*   Page:

    [Creating and configuring SSH keys (Windows/MacOS/Linux)](/wiki/spaces/GIJDC/pages/183271450)

*   Page:

    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849)

*   Page:

    [Setting Project Permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions)

*   Page:

    [How to get a quote?](/wiki/spaces/GIJDC/pages/1165721603)

*   Page:

    [Ways to Index Git Data to Jira Issues](/wiki/spaces/GIJDC/pages/1207828916/Ways+to+Index+Git+Data+to+Jira+Issues)

*   Page:

    [Proxy settings on adding integrations (except AWS CodeCommit)](/wiki/spaces/GIJDC/pages/1808007195)

*   Page:

    [Configure Source Code Diff Viewing](/wiki/spaces/GIJDC/pages/2054881287/Configure+Source+Code+Diff+Viewing)