---

title: Generating SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Configure and generate SSH keys for the following git hosting systems by following the reference links on each sub-section:

|     |
| --- |
| **Beanstalk** |
| *   For MacOS, see [Working with Git on MacOS](http://guides.beanstalkapp.com/version-control/git-on-mac.html).<br>    <br>*   For Windows, see [Working with Git on Windows](http://guides.beanstalkapp.com/version-control/git-on-windows.html).<br>    <br>*   For Linux, see [Working with Git on Linux](http://guides.beanstalkapp.com/version-control/git-on-linux.html). |
| **Bitbucket** |
| *   For MacOS/Linux, see [Setting up SSH for Git on MacOS/Linux](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/#Set-up-SSH-on-macOS-Linux).<br>    <br>*   For Windows, see [Set up SSH for Git on Windows](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/). |
| **Gerrit** |
| The Git Integration for Jira app supports Gerrit web linking.<br><br>*   For information about Gerrit software, see [Gerrit Software Wiki](http://en.wikipedia.org/wiki/Gerrit_(software)) and [Gerrit at Code Review](https://code.google.com/p/gerrit/).<br>    <br>*   For general reference and installation, see [Gerrit documentation](https://gerrit-review.googlesource.com/Documentation/). [Ubuntu installation](https://gerrit-review.googlesource.com/Documentation/linux-quickstart.html) and fixing [registration error](https://code.google.com/p/gerrit/issues/detail?id=1549).<br>    <br>*   For information on SSH on Gerrit, see [SSH and Gerrit](https://gerrit-documentation.storage.googleapis.com/Documentation/2.11/user-upload.html#_ssh).<br>    <br>*   For details on User Change-IDs, see [Change-IDs in Gerrit](https://git.eclipse.org/r/Documentation/user-changeid.html). |
| **GitBlit** |
| *   For information about Gitblit, see [GitBlit official website](http://gitblit.github.io/gitblit/).<br>    <br>*   For general reference and installation, see [GitBlit Configuration](http://gitblit.com/administration.html), [Using HTTP/HTTPS Transport](http://gitblit.com/setup_transport_http.html) and [Built-in Authentication](http://gitblit.com/setup_authentication.html).<br>    <br>*   For information on SSH on GitBlit, see [GitBlit: Using the SSH Transport](http://gitblit.com/setup_transport_ssh.html).<br>    <br>*   For GitBlit related FAQ, see [GitBlit Frequently Asked Questions](http://gitblit.com/faq.html). |
| **GitHub** |
| [Check for existing SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys) before you proceed to generate new keys.<br><br>See GitHub supported platforms for generating SSH keys by following [this article](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent). |
| **GitLab** |
| *   See reference, [Installing Git for MacOS/Windows/Linux](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).<br>    <br>*   For creating SSH keys, see [Generating SSH Public Key](https://docs.gitlab.com/ce/ssh/README.html). Also see the video demonstration [here](https://about.gitlab.com/blog/2014/03/04/add-ssh-key-screencast/). |
| **GitLab CE/EE** |
| Follow the above GitLab references for GitLab CE/EE. Then verify that your GitLab server should have the following SSH settings:<br><br>![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396609/gitlab-server-ssh-settings(c).png?version=1&modificationDate=1630642801142&cacheVersion=1&api=v2&width=680&height=471)<br><br>*   Enabled Git access protocols -- **Both SSH and HTTP(s)**<br>    <br>*   RSA SSH keys -- **Are allowed**<br>    <br><br>Other SSH key formats may be supported by Git Integration for Jira app, but prefer to use RSA format for your SSH git connections. |
| **Git-scm** |
| *   See reference, [Installing Git for MacOS/Windows/Linux](https://git-scm.com/book/en/Getting-Started-Installing-Git).<br>    <br>*   For creating SSH keys, see [Connecting to GitHub with SSH](https://help.github.com/en/articles/connecting-to-github-with-ssh). |
| **Gitolite** |
| *   For full reference and installation, see [All About Gitolite](https://gitolite.com/gitolite/index.html).<br>    <br>*   For information on SSH on Gitolite, see [SSH and Gitolite](https://gitolite.com/gitolite/ssh.html).<br>    <br>*   For details on user key management, see [Managing User Keys in Gitolite](https://gitolite.com/gitolite/contrib/ukm.html). |
| **VSTS/TFS/Azure DevOps/Azure Repos** |
| The SSH support starts with TFS 2013 and later versions.<br><br>*   For information about TFS/Azure DevOps Server, see [MS Team Foundation Server](https://azure.microsoft.com/en-us/services/devops/server/).<br>    <br>*   For general reference and terms, see [Git Experience Futures](https://devblogs.microsoft.com/devops/git-experience-futures/). |

Users can use HTTPS or SSH to securely connect to git repositories.  HTTPS connections will require the user's login credentials, while SSH connections will require SSH keys.

[« Working with SSH keys (index)](/wiki/spaces/GIJDC/pages/1930396577/Working+with+SSH+keys)

[Adding a private SSH key »](/wiki/spaces/GIJDC/pages/1930396698/Adding+a+private+SSH+key)

### More related topics about SSH integration

*   Page:

    [Working with SSH keys](/wiki/spaces/GIJDC/pages/1930396577/Working+with+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Generating SSH keys](/wiki/spaces/GIJDC/pages/1930396609/Generating+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Adding a private SSH key](/wiki/spaces/GIJDC/pages/1930396698/Adding+a+private+SSH+key) (Git Integration for Jira Data Center)

*   Page:

    [Adding a public SSH Key](/wiki/spaces/GIJDC/pages/1930396728/Adding+a+public+SSH+Key) (Git Integration for Jira Data Center)

*   Page:

    [SSH keys configuration](/wiki/spaces/GIJDC/pages/1930396746/SSH+keys+configuration) (Git Integration for Jira Data Center)

*   Page:

    [Adding and associating SSH keys](/wiki/spaces/GIJDC/pages/1930396771/Adding+and+associating+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Removing SSH keys](/wiki/spaces/GIJDC/pages/1930396835/Removing+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Reconfigure Git repositories and SSH keys](/wiki/spaces/GIJDC/pages/1930396868/Reconfigure+Git+repositories+and+SSH+keys) (Git Integration for Jira Data Center)