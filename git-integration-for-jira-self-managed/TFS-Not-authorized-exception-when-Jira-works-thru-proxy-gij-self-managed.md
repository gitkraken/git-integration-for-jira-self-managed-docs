---

title: TFS - Not authorized exception when Jira works thru proxy
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

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

```python
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

Enter **`<your-git-server-host>`** to **`nonProxyHosts`** entries.

Usually, the **nonProxyHosts** are the list of servers that the JVM should **not** send through the proxy. This is because they are in the same data center and a private address.

Wildcards are supported:

```python
-Dhttp.nonProxyHosts=*.git.server.host
-Dhttps.nonProxyHosts=*.git.server.host
```

Or instead, use pipe and quotes for multiple hosts:

```python
-Dhttp.nonProxyHosts="your.git.server.host1|your.git.server.host2"
-Dhttps.nonProxyHosts="your.git.server.host1|your.git.server.host2"
```

<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>
<br>

<p>&nbsp;</p>

## More articles about troubleshooting, workarounds and solutions

[Why I am getting the error, “git-upload-pack not permitted”?](/git-integration-for-jira-data-center/why-i-am-getting-the-error-git-upload-pack-not-permitted-gij-self-managed/)

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

**TFS - Not authorized exception when Jira works thru proxy** (this page)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

<br>
<br>

