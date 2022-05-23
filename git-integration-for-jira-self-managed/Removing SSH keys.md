---

title: Removing SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
SSH keys cannot be modified or updated. To change the keys, remove and add them again.

To delete the SSH key from the app configuration, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Delete**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396835/ssh-addkey-list-del-key.png?version=1&modificationDate=1630642808913&cacheVersion=1&api=v2&width=680&height=294)

If the key is deleted, all repository references will also be removed. Repositories that don't have the key associated to them will use the common keys by default.

[« Adding and associating SSH keys](/wiki/spaces/GIJDC/pages/1930396771/Adding+and+associating+SSH+keys)

[Reconfigure Git repositories and SSH keys »](/wiki/spaces/GIJDC/pages/1930396868/Reconfigure+Git+repositories+and+SSH+keys)
