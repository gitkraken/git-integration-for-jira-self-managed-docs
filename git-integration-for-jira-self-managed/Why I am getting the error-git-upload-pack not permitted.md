---

title: Why I am getting the error, "git-upload-pack not permitted"?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Why I am getting the error, "git-upload-pack not permitted"?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2051375177>

* * *

You are getting this error because of wrong login credentials or a permission issue.

**What’s on this page:**

### Having Invalid Credentials

The most common cause is a wrong login credentials input.

REPOSITORY LEVEL Go to the **Manage** **Git repositories** configuration list. Select ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** for a particular repository then **Edit repository settings**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2051375177/gitserver-git-uploack-pack-err-01.png?version=1&modificationDate=1642158042088&cacheVersion=1&api=v2&width=680&height=501)

Check the repository properties for the **Username** and **Password/PAT** fields and verify that they are filled with correct values. Retype login credentials just to make sure and save the settings.

  
INTEGRATION LEVEL Go to the **Manage** **Git repositories** configuration list. Select ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** for a particular repository then **Edit integration connection settings**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2051375177/gitserver-git-upload-pack-err-02.png?version=1&modificationDate=1642158455218&cacheVersion=1&api=v2&width=680&height=264)

Check the integration properties for the **Username** and **Password/PAT** fields and verify that they are filled with correct values. Retype login credentials just to make sure and save the settings.

### Not Having Enough Access Permissions

The other cause is not having enough access permissions to clone repositories. Try to clone a repository via the git client console using the correct `<JIRA_user>` on a Jira server. If an error is raised, the Git Integration for Jira app will also do the same.

To install Git Integration for Jira app and clone a repository:

1.  Go to your Jira server.
    
2.  Install the git client: `sudo apt-get install git` or `sudo yum install git`.
    
3.  Verify the correct `<JIRA_user>` (Go to **Jira Administration** ➜ **System** ➜ **System Info**. Scroll to **User Name**. _**How?**_).
    
4.  Re-login as `<JIRA_user>`
    
5.  Run `git clone http://<your-repo>/`
    

The command should be successful. If not, ask your administrator to setup your environment.

### Using Proxies

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

Enter `<your-git-server-host>` to `nonProxyHosts` entries.

### Examining Logs and Errors

To get a better view of the cause of the error:

1.   See the debug logs of the jgit library in Jira generated during cloning/re-indexing of your repository.
    
    Enable debug logging for jgit library in Jira:
    
    1.  Go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Jira Administration** ➜ **System**.
        
    2.  On the sidebar, under _**System Support**_, click **Logging and profiling**.
        
    3.  Scroll down to the _**Default Loggers**_ section, then click **Configure**.
        
    4.  Enter `org.apache.http` for _**Package Name**_ then set _**Logging Level**_ to **DEBUG**.
        
    5.  Click **Add** to add this configuration to the _**Debug Loggers**_ list.
        
    
    Collect logs generated during reindex of your repository:
    
    1.  Write down the current time right before doing a reindex – let's call it `time1`.
        
    2.  Do a reindex for your integration/repository via dashboard menu Git ➜ Manage repositories ➜ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Reindex integration/repository**.
        
    3.  After the reindex is complete, write down the current time – let's call it `time2`.
        
    4.  Collect logs created between `time1` and `time2`.
        
2.  See the verbose logs of successful clone of your repository cloned by the console git client.
    
    1.  From the command line, run `set GIT_CURL_VERBOSE=1`
        
    2.  Do a git clone of the affected repository `git clone http://<your-repo>`.
        

The output is a verbose log of this process.

Compare the debug and the verbose logs and see the difference between them or send us both logs to [support@bigbrassband.com](mailto:support@bigbrassband.com) for in-depth review.

Examine used authentication schemes. If you are seeing Basic authentication, you can verify that the right login credentials are passed.

### How to find supported authentication schemes?

Below is an example of the debug logs of the jgit library in JIRA generated during cloning/re-indexing of your repository:

```py
...
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [http.impl.client.TargetAuthenticationStrategy] Authentication schemes in the order of preference: [Negotiate, Kerberos, NTLM, Digest, Basic]
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [http.impl.client.TargetAuthenticationStrategy] Challenge for Negotiate authentication scheme not available
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [http.impl.client.TargetAuthenticationStrategy] Challenge for Kerberos authentication scheme not available
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [http.impl.client.TargetAuthenticationStrategy] Challenge for NTLM authentication scheme not available
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [http.impl.client.TargetAuthenticationStrategy] Challenge for Digest authentication scheme not available
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [http.client.protocol.RequestAddCookies] CookieSpec selected: default
...
```

In this case, the Basic authentication was used because all other authentication methods have been rejected.

### How to find login credentials used in Basic authentication?

Below is another example of the debug logs of the jgit library in JIRA generated during cloning/re-indexing of your repository:

```java
...
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> GET /<your-git-server-url>/<your-repo-name>.git/info/refs?service=git-upload-pack HTTP/1.1
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Accept-Encoding: gzip
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Pragma: no-cache
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> User-Agent: JGit/unknown
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Authorization: Basic amlyYTpqaXJhcGFzc3dvcmQ=
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Accept: application/x-git-upload-pack-advertisement, */*
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Host: 123.123.123.123
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Connection: Keep-Alive
...
```

From the above log:

1.  Find the header, **Authorization**.
    
2.  In the example it contains `Basic amlyYTpqaXJhcGFzc3dvcmQ=`, where `amlyYTpqaXJhcGFzc3dvcmQ=` is the login credentials encoded in base64. Decode the base64 string using any online decoder. `Result: jira:jirapassword`.
    
3.  Verify that `jira` is the expected username and `jirapassword` is the expected password.
    

*   Page:
    
    [I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?](/wiki/spaces/GIJDC/pages/2051145752)
    
*   Page:
    
    [Can the app be configured to handle or scan multiple keys for one project? How is this supposed to work?](/wiki/spaces/GIJDC/pages/2052128838)
    
*   Page:
    
    [Where is the location of the local git repository?](/wiki/spaces/GIJDC/pages/2051080265)
    
*   Page:
    
    [How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?](/wiki/spaces/GIJDC/pages/2052128856)
    
*   Page:
    
    [I get the following error: "Host or port specified in <git\_repository\_url> are inaccessible". Do I also need a git instance on the Jira server?](/wiki/spaces/GIJDC/pages/2051375166)
    
*   Page:
    
    [We use GitBlit without SSH keys and use only HTTPS instead. Does Git Integration for Jira app support this?](/wiki/spaces/GIJDC/pages/2051440710)
    
*   Page:
    
    [I am using Jira which is hosted on Windows. I changed the password of the Active Directory account running Jira. Now, I cannot access my repository. Why?](/wiki/spaces/GIJDC/pages/2051768359)