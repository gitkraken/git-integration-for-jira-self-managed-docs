---

title: Generating SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Configure and generate SSH keys for the following git hosting systems by following the reference links on each sub-section:

## Beanstalk

*   For MacOS, see [Working with Git on MacOS](http://guides.beanstalkapp.com/version-control/git-on-mac.html).

*   For Windows, see [Working with Git on Windows](http://guides.beanstalkapp.com/version-control/git-on-windows.html).

*   For Linux, see [Working with Git on Linux](http://guides.beanstalkapp.com/version-control/git-on-linux.html).

## Bitbucket

*   For MacOS/Linux, see [Setting up SSH for Git on MacOS/Linux](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/#Set-up-SSH-on-macOS-Linux).

*   For Windows, see [Set up SSH for Git on Windows](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/).

## Gerrit

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app supports Gerrit web linking.
    </div>
    </div>
</div>

*   For information about Gerrit software, see [Gerrit Software Wiki](http://en.wikipedia.org/wiki/Gerrit_(software)) and [Gerrit at Code Review](https://code.google.com/p/gerrit/).

*   For general reference and installation, see [Gerrit documentation](https://gerrit-review.googlesource.com/Documentation/). [Ubuntu installation](https://gerrit-review.googlesource.com/Documentation/linux-quickstart.html) and fixing [registration error](https://code.google.com/p/gerrit/issues/detail?id=1549).

*   For information on SSH on Gerrit, see [SSH and Gerrit](https://gerrit-documentation.storage.googleapis.com/Documentation/2.11/user-upload.html#_ssh).

*   For details on User Change-IDs, see [Change-IDs in Gerrit](https://git.eclipse.org/r/Documentation/user-changeid.html).

## GitBlit

*   For information about Gitblit, see [GitBlit official website](http://gitblit.github.io/gitblit/).

*   For general reference and installation, see [GitBlit Configuration](http://gitblit.com/administration.html), [Using HTTP/HTTPS Transport](http://gitblit.com/setup_transport_http.html) and [Built-in Authentication](http://gitblit.com/setup_authentication.html).

*   For information on SSH on GitBlit, see [GitBlit: Using the SSH Transport](http://gitblit.com/setup_transport_ssh.html).

*   For GitBlit related FAQ, see [GitBlit Frequently Asked Questions](http://gitblit.com/faq.html).

## GitHub

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <a href='https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys' target='_blank'>Check for existing SSH keys</a> before you proceed to generate new keys.
    </div>
    </div>
</div>

See GitHub supported platforms for generating SSH keys by following [this article](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

## GitLab

*   See reference, [Installing Git for MacOS/Windows/Linux](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

*   For creating SSH keys, see [Generating SSH Public Key](https://docs.gitlab.com/ce/ssh/README.html). Also see the video demonstration [here](https://about.gitlab.com/blog/2014/03/04/add-ssh-key-screencast/).

## GitLab CE/EE

Follow the above GitLab references for GitLab CE/EE. Then verify that your GitLab server should have the following SSH settings:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396609/gitlab-server-ssh-settings(c).png?version=1&modificationDate=1630642801142&cacheVersion=1&api=v2&width=680&height=471)

*   Enabled Git access protocols -- **Both SSH and HTTP(s)**

*   RSA SSH keys -- **Are allowed**

Other SSH key formats may be supported by Git Integration for Jira app, but prefer to use RSA format for your SSH git connections.

## Git-scm

*   See reference, [Installing Git for MacOS/Windows/Linux](https://git-scm.com/book/en/Getting-Started-Installing-Git).

*   For creating SSH keys, see [Connecting to GitHub with SSH](https://help.github.com/en/articles/connecting-to-github-with-ssh).

## Gitolite

*   For full reference and installation, see [All About Gitolite](https://gitolite.com/gitolite/index.html).

*   For information on SSH on Gitolite, see [SSH and Gitolite](https://gitolite.com/gitolite/ssh.html).

*   For details on user key management, see [Managing User Keys in Gitolite](https://gitolite.com/gitolite/contrib/ukm.html).

## VSTS \| TFS \| Azure DevOps/Azure Repos

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The SSH support starts with TFS 2013 and later versions.
    </div>
    </div>
</div>

*   For information about TFS/Azure DevOps Server, see [MS Team Foundation Server](https://azure.microsoft.com/en-us/services/devops/server/).

*   For general reference and terms, see [Git Experience Futures](https://devblogs.microsoft.com/devops/git-experience-futures/).

* * *

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Users can use HTTPS or SSH to securely connect to git repositories. HTTPS connections will require the user's login credentials, while SSH connections will require SSH keys.
    </div>
    </div>
</div>

* * *

[Previous: Working with SSH keys (index)](/git-integration-for-jira-self-managed/working-with-ssh-keys)

[Next: Adding a private SSH key »](/git-integration-for-jira-self-managed/adding-a-private-ssh-key)

