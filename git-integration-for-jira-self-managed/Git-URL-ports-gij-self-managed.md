---

title: Git URL ports
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
If your Jira and Git servers are running through a firewall, configure the firewall to allow access using the URL schemes for git repositories. For authentication issues, make sure to check first the correct port for its connection.

Below are the default ports for common git URL protocols:

| Protocol | Default Port |
| :--- | :--- |
| ssh:\/\/ | port 22 |
| git:\/\/ | port 9418 |
| http:\/\/ | port 80 |
| https:\/\/ | port 443 |

<br>

Test git connection and repository URL by doing the following:

1.  Install git client (_or run_ `sudo apt-get install git`)

2.  Place your ssh key into `~/.ssh`

3.  Clone the repository (or run `git clone <your_repository_url>`)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app will run successfully if the above connection test ran without errors.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Working with SSH keys](/git-integration-for-jira-data-center/working-with-ssh-keys-gij-self-managed)

[**Next:** Setting up repositories](/git-integration-for-jira-data-center/setting-up-repositories-gij-self-managed)


