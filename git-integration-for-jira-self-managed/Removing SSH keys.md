---

title: Removing SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
SSH keys cannot be modified or updated. To change the keys, remove and add them again.

To delete the SSH key from the app configuration, click Actions ➜ **Delete**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396835/ssh-addkey-list-del-key.png?version=1&modificationDate=1630642808913&cacheVersion=1&api=v2&width=680&height=294)

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the key is deleted, all repository references will also be removed. Repositories that don't have the key associated to them will use the common keys by default.
    </div>
    </div>
</div>

