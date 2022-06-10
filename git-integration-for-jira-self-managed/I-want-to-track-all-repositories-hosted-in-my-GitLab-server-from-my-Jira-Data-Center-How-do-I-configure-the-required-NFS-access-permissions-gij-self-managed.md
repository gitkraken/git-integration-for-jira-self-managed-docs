---

title: I want to track all repositories hosted in my GitLab server from my Jira Data Center. How do I configure the required NFS access permissions?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Where a GitLab server is configured with NFS server and the Jira Data Center is configured with NFS client, there are two possible solutions:

| **Solution 1** |
| --- |
| The `'all_squash'` option must not be used in the NFS server **'etc/exports'** file for GitLab folders. The NFS client should have the **'git'** group with the same GID as the **'git'** group on the NFS server. The Jira user on the NFS client should be added to the group **'git'**. |
| _**Example:**_<br><br>```java<br>/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,root_squash,async)<br>``` |

| **Solution 2** |
| --- |
| Use the `'all_squash,async,anonuid=$uid,anongid=$gid'` option on NFS server, where _$uid_ and _$gid_are user ID and group ID for **'git'** user and **'git'** group respectively _(or another user/group which you are using to access GitLab repositories on GitLab server)_. |
| _**Example:**_<br><br>```java<br>/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,all_squash,async,anonuid=497,anongid=497)<br>``` |

In both cases either `'ro'` or `'rw'` options may be used on NFS server.

