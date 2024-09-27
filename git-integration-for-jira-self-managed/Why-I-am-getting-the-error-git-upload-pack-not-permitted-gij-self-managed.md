---

title: Why I am getting the error, "git-upload-pack not permitted"?
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

You are getting this error because of wrong login credentials or a permission issue.

**What’s on this page:**
- [Having Invalid Credentials](#having-invalid-credentials)
- [Not Having Enough Access Permissions](#not-having-enough-access-permissions)
- [Using Proxies](#using-proxies)
- [Examining Logs and Errors](#examining-logs-and-errors)
  - [How to find supported authentication schemes?](#how-to-find-supported-authentication-schemes)
  - [How to find login credentials used in Basic authentication?](#how-to-find-login-credentials-used-in-basic-authentication)
- [More articles about troubleshooting, workarounds and solutions](#more-articles-about-troubleshooting-workarounds-and-solutions)

&nbsp;
* * *
&nbsp;

### Having Invalid Credentials

The most common cause is a wrong login credentials input.

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>REPOSITORY LEVEL</b> Go to the **Manage Git repositories** configuration list. Select ![](/wp-content/uploads/actions-icon.png) **Actions** for a particular repository then **Edit repository settings**.

![](/wp-content/uploads/gij-gitserver-git-uploack-pack-err-01.png)

Check the repository properties for the **Username** and **Password/PAT** fields and verify that they are filled with correct values. Retype login credentials just to make sure and save the settings.  

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>INTEGRATION LEVEL</b> Go to the **Manage** **Git repositories** configuration list. Select **Actions** for a particular repository then **Edit integration connection settings**.

![](/wp-content/uploads/gij-gitserver-git-upload-pack-err-02.png)

Check the integration properties for the **Username** and **Password/PAT** fields and verify that they are filled with correct values. Retype login credentials just to make sure and save the settings.

&nbsp;

### Not Having Enough Access Permissions

The other cause is not having enough access permissions to clone repositories. Try to clone a repository via the git client console using the correct `<JIRA_user>` on a Jira server. If an error is raised, the Git Integration for Jira app will also do the same.

To install Git Integration for Jira app and clone a repository:

1.  Go to your Jira server.

2.  Install the git client: `sudo apt-get install git` or `sudo yum install git`.

3.  Verify the correct `<JIRA_user>` (Go to Jira Administration ➜ System ➜ **System Info**. Scroll to **User Name**. _**How?**_).

4.  Re-login as `<JIRA_user>`

5.  Run `git clone http://<your-repo>/`


The command should be successful. If not, ask your administrator to setup your environment.

&nbsp;

### Using Proxies

If you are using proxy, configure your Jira with the following parameter format:

```python
Dhttp.proxyHost=\<your-proxy-host\>
Dhttps.proxyHost=\<your-proxy-host\>
Dhttp.proxyPort=\<your-proxy-port\>
Dhttps.proxyPort=\<your-proxy-port\>
Dhttp.proxyUser=*****
Dhttps.proxyUser=*****
Dhttp.proxyPassword=*****
Dhttps.proxyPassword=*****
Dhttp.nonProxyHosts=*.some.mask|localhost|1.1.1.1\<someIP\>
Dhttps.nonProxyHosts=*.some.mask|localhost|1.1.1.1\<someIP\>
```

Enter `<your-git-server-host>` to `nonProxyHosts` entries.

&nbsp;

### Examining Logs and Errors

To get a better view of the cause of the error:

*   See the debug logs of the jgit library in Jira generated during cloning/re-indexing of your repository.

    Enable debug logging for jgit library in Jira:

    1.  Go to Jira Administration ➜ **System**.

    2.  On the sidebar, under _**System Support**_, click **Logging and profiling**.

    3.  Scroll down to the _**Default Loggers**_ section, then click **Configure**.

    4.  Enter `org.apache.http` for _**Package Name**_ then set _**Logging Level**_ to **DEBUG**.

    5.  Click **Add** to add this configuration to the _**Debug Loggers**_ list.

    &nbsp;
    
    Collect logs generated during reindex of your repository:

    1.  Write down the current time right before doing a reindex – let's call it `time1`.

    2.  Do a reindex for your integration/repository via dashboard menu Git ➜ Manage repositories ➜Actions ➜ **Reindex integration/repository**.

    3.  After the reindex is complete, write down the current time – let's call it `time2`.

    4.  Collect logs created between `time1` and `time2`.<br><br>

*   See the verbose logs of successful clone of your repository cloned by the console git client.

    *   From the command line, run `set GIT_CURL_VERBOSE=1`

    *   Do a git clone of the affected repository `git clone http://<your-repo>`.

&nbsp;

The output is a verbose log of this process.

Compare the debug and the verbose logs and see the difference between them or send us both logs to [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com) for in-depth review.

Examine used authentication schemes. If you are seeing Basic authentication, you can verify that the right login credentials are passed.

&nbsp;

#### How to find supported authentication schemes?

Below is an example of the debug logs of the jgit library in JIRA generated during cloning/re-indexing of your repository:

```java
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

&nbsp;

#### How to find login credentials used in Basic authentication?

Below is another example of the debug logs of the jgit library in JIRA generated during cloning/re-indexing of your repository:

```java
...
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> GET /\<your-git-server-url\>/\<your-repo-name\>.git/info/refs?service=git-upload-pack HTTP/1.1
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Accept-Encoding: gzip
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Pragma: no-cache
2016-10-24 19:46:21,504 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> User-Agent: JGit/unknown
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Authorization: Basic amlyYTpqaXJhcGFzc3dvcmQ=
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Accept: application/x-git-upload-pack-advertisement, \*/\*
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Host: 123.123.123.123
2016-10-24 19:46:21,519 xiplink-gitplugin-RevisionIndexerImpl:thread - 0 DEBUG      [org.apache.http.headers] http-outgoing-9 >> Connection: Keep-Alive
...
```

From the above log:

1.  Find the header, **Authorization**.

2.  In the example it contains `Basic amlyYTpqaXJhcGFzc3dvcmQ=`, where `amlyYTpqaXJhcGFzc3dvcmQ=` is the login credentials encoded in base64. Decode the base64 string using any online decoder. `Result: jira:jirapassword`.

3.  Verify that `jira` is the expected username and `jirapassword` is the expected password.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

&nbsp;

### More articles about troubleshooting, workarounds and solutions

**Why I am getting the error, “git-upload-pack not permitted”?** (this page)

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/avoid-outofmemory-exceptions-by-configuring-or-memory-allocation-with-jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

[Duplicate entry 0 for key PRIMARY exceptions in log](/git-integration-for-jira-data-center/Duplicate-entry-0-for-key-PRIMARY-exceptions-in-log-gij-self-managed)

[Error while reindexing – Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Gitolite integration: Why the Git integration app not see the master branch?](/git-integration-for-jira-data-center/Gitolite-integration--why-the-Git-integration-app-not-see-the-master-branch-gij-self-managed)

[Health Check: Database Collation](/git-integration-for-jira-data-center/Health-check--database-collation-gij-self-managed)

[Indexing error – Too many open files](/git-integration-for-jira-data-center/Indexing-error-Too-many-open-files-gij-self-managed)

[Installation fails when installing manually](/git-integration-for-jira-data-center/Installation-fails-when-installing-manually-gij-self-managed)

[Jira index error: IndexNotFoundException: no segments* file found](/git-integration-for-jira-data-center/Jira-index-error--IndexNotFoundException--no-segments-file-found)

[Malformed input or input contains unmappable characters](/git-integration-for-jira-data-center/Malformed-input-or-input-contains-unmappable-characters-gij-self-managed)

[Personal access token failing Azure DevOps integration with Not Authorized error](/git-integration-for-jira-data-center/Personal-access-token-failing-azure-devops-integration-with-Not-Authorized-error-gij-self-managed)

[Problems with shared home on Azure Storage](/git-integration-for-jira-data-center/Problems-with-shared-home-on-azure-storage-gij-self-managed)

[Pull request index error: org.json.JSONException](/git-integration-for-jira-data-center/Pull-request-index-error--JSONException-gij-self-managed)

[Repositories missing from Azure DevOps integration](/git-integration-for-jira-data-center/Repositories-missing-from-azure-devops-integration-gij-self-managed)

["Service proxy has been destroyed" exceptions in log](/git-integration-for-jira-data-center/service-proxy-has-been-destroyed-exceptions-in-log-gij-self-managed)

[SQLException 'Incorrect string value' in merge requests](/git-integration-for-jira-data-center/sqlexception-incorrect-string-value-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

<br>
<br>

