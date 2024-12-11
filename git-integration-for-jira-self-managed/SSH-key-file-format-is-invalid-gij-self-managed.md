---

title: SSH key file format is invalid
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- TROUBLESHOOTING -->

### Problem

Git Integration for Jira application SSH keys:

1.  Must not be created using the OpenSSH format
2.  Must be the private SSH key
3.  Must use the supported certificate format: RSA
4.  Must use the supported storage format: OpenSSL PEM

### Diagnosis

Jira admins will see a message similar to the one below when adding the SSH key:


> _The key format is invalid. Please check your private key._

<img src='/wp-content/uploads/gij-ssh-key-is-invalid.png' style='display:block;margin:25px auto;max-width:100%' width=521 height=521 />

Full error (stack trace) available in the Manage Git Repositories wizard or in Jira logs `/application-logs/atlassian-jira.log`:

**Error:**

```java
com.bigbrassband.jira.git.exceptions.repository.InvalidPrivateKeyException: Private SSH key is invalid or empty
	at com.bigbrassband.jira.git.services.ssh.KeyManagerImpl.needPassphrase(KeyManagerImpl.java:103)
	at com.bigbrassband.jira.git.rest.wizard.WizardResource.validateRepoOrigin(WizardResource.java:104)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	...
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1498)
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)
	at java.lang.Thread.run(Thread.java:748)
Caused by: com.jcraft.jsch.JSchException: invalid privatekey: [C@17h421rm
	at com.jcraft.jsch.KeyPair.load(KeyPair.java:664)
	at com.bigbrassband.jira.git.services.ssh.KeyManagerImpl.needPassphrase(KeyManagerImpl.java:99)
	... 264 more
```

### Cause

Jira admin has provided an SSH public key or an SSH private key with an incorrect format.

### Solutions

1. Create a new SSH key:

    **On Linux and macOS:**

    Use the following command to create a certificate:

    ```powershell
    ssh-keygen -t rsa -b 4096 -m pem -C [your_email@example.com](mailto:your_email@example.com)
    ```

    <div class="bbb-callout bbb--alert">
      <div class="irow">
        <div class="ilogobox">
          <span class="logoimg"></span>
        </div>
        <div class="imsgbox">
          MacOS often incorrectly creates an OpenSSH format certificate. For more details, see information on this <a href='https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key' title='Opens in new tab/window.' target='_blank'><b>common problem</b></a>.
        </div>
      </div>
    </div>
    
    **On Windows:**

    Download **[PuTTY](https://www.putty.org)** and use PuTTYgen to generate an SSH key pair:

    1.  Set _**Type of key...**_ to **RSA**.

    2.  Set **_Number of bits..._** to **4096**.

    3.  Click **Generate**. Move mouse pointer on the blank area as instructed.

    4.  Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.

    5.  Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.

    6.  Save your generated public and private key to a file by clicking the respective options.

    7.  Copy the generated key. This is the public key that you will be using on the SSH configuration page of your git host.

    8.  For the private key, PuTTY creates a private key in its own ".ppk" format. Convert it to ".pem" via menu **Conversions** \> **Export OpenSSH key** in PuTTYgen. Add/upload this file to Git Integration for Jira app \> **SSH Keys** or when prompted on connecting SSH git repositories in Jira.


2. Create a new SSH key using RSA certificate format. See **Solution #1**.

3. Use OpenSSL PEM storage format. See **Solution #1**.

4. Provide the public SSH key to the SSH configuration of your git host.

5. Provide the private SSH key to the Git Integration for Jira app ➜ **SSH Keys** or when prompted on connecting SSH git repositories in Jira.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

&nbsp;

### More articles about troubleshooting, workarounds and solutions

[Why I am getting the error, “git-upload-pack not permitted”?](/git-integration-for-jira-data-center/why-i-am-getting-the-error-git-upload-pack-not-permitted-gij-self-managed/)

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/avoid-outofmemory-exceptions-by-configuring-or-memory-allocation-with-jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

[Duplicate entry 0 for key PRIMARY exceptions in log](/git-integration-for-jira-data-center/Duplicate-entry-0-for-key-PRIMARY-exceptions-in-log-gij-self-managed)

[Error while reindexing – Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Error creating git branches and also using NFS](/git-integration-for-jira-data-center/error-creating-git-branches-gitlabpropertiesnotinitializedexception-and-using-nfs-gij-self-managed)

[Fix performance issues for nested cloned repositories with enabled Git Service Permissions mode](/git-integration-for-jira-data-center/Fix-performance-issues-for-nested-cloned-repositories-with-enabled-secure-mode-gij-self-managed)

[Fixing reindex issues using Indexing Queue Viewer](/git-integration-for-jira-data-center/fixing-reindex-issues-using-indexing-queue-viewer)

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

**SSH key file format is invalid** (this page)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

[When a GIJ license expires, it shows up as a session error to the user](/git-integration-for-jira-data-center/when-a-license-expires-a-session-error-is-shown-to-the-user-gij-self-managed)

[edDSA provider not supported WARN in logs](/git-integration-for-jira-data-center/edDSA-provider-not-supported-WARN-in-logs-gij-self-managed)

