---

title: SSH key file format is invalid
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# SSH key file format is invalid

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/187957296/SSH+key+file+format+is+invalid>

* * *

## Problem

Git Integration for Jira application SSH keys:

1.  Must not be created using the OpenSSH format
2.  Must be the private SSH key
3.  Must use the supported certificate format: RSA
4.  Must use the supported storage format: OpenSSL PEM

## Diagnosis

Jira admins will see a message similar to the one below when adding the SSH key:  
  

> The key format is invalid. Please check your private key.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/140574747/private-key.png?version=1&modificationDate=1560776913176&cacheVersion=1&api=v2&height=400)

Full error (stack trace) available in the Manage Git Repositories wizard or in Jira logs `/application-logs/atlassian-jira.log`:

**Error**

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

  

## Cause

Jira admin has provided an SSH public key or an SSH private key with an incorrect format.

## Solutions

1\. Create a new SSH key:

**On Linux and macOS:**

Use the following command to create a certificate:

ssh-keygen \-t rsa \-b 4096 \-m pem \-C [your\_email@example.com](mailto:your_email@example.com)

  

MacOS often incorrectly creates an OpenSSH format certificate. For more details, see information on this **[common problem](https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key "Opens in new tab/window.")**.

**On Windows:**

Download **[PuTTY](https://www.putty.org)** and use PuTTYgen to generate an SSH key pair:

1.  Set _**Type of key...**_ to **RSA**.
    
2.  Set **_Number of bits..._** to **4096**.
    
3.  Click **Generate**. Move mouse pointer on the blank area as instructed.
    
4.  Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.
    
5.  Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.
    
6.  Save your generated public and private key to a file by clicking the respective options.
    
7.  Copy the generated key. This is the public key that you will be using on the SSH configuration page of your git host.
    
8.  For the private key, PuTTY creates a private key in its own ".ppk" format. Convert it to ".pem" via menu **Conversions** > **Export OpenSSH key** in PuTTYgen. Add/upload this file to Git Integration for Jira app > **SSH Keys** or when prompted on connecting SSH git repositories in Jira.
    

2\. Create a new SSH key using RSA certificate format. See Solution #1.

3\. Use OpenSSL PEM storage format. See Solution #1.

4\. Provide the public SSH key to the SSH configuration of your git host.

5\. Provide the private SSH key to the Git Integration for Jira app > **SSH Keys** or when prompted on connecting SSH git repositories in Jira.

  

Contact Us

If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com)

  

## Related articles

*   Page:
    
    [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/wiki/spaces/GIJDC/pages/873332786/Avoid+OutOfMemory+exceptions+by+configuring+or+memory+allocation+with+Jira+to+accommodate+large+repositories)
    
*   Page:
    
    [SQLException 'Incorrect string value' in merge requests](/wiki/spaces/GIJDC/pages/843448333/SQLException+%27Incorrect+string+value%27+in+merge+requests)
    
*   Page:
    
    ["Dangerous use of multiple connections" error on local database](/wiki/spaces/GIJDC/pages/821919745)
    
*   Page:
    
    ["Service proxy has been destroyed" exceptions in log](/wiki/spaces/GIJDC/pages/458883074)
    
*   Page:
    
    [Indexing error - Too many open files](/wiki/spaces/GIJDC/pages/318013497/Indexing+error+-+Too+many+open+files)