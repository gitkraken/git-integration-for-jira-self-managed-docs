---

title: Working with Custom API Path
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Custom API Path is a relative path that starts with "/".  The maximum allowed length is 2000 characters. The integration will use the relative REST API path to retrieve the list of tracked repositories.

The Custom API Path is called in the integration setup, settings changes, on a regular scheduled reindex and for a manual reindex.


* * *

## Accessible locations

|     |
| --- |
| *   Add new integration Wizard ➜ Connection screen ➜ _Advanced_ ➜ **Custom API Path**. For example: |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/135331922/gitserver-auto-connect-github-example.png?version=2&modificationDate=1642507945521&cacheVersion=1&api=v2&width=680&height=455) |

|     |
| --- |
| *   Manage repositories page ➜ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ Edit integration connection settings ➜ **Custom API Path**. |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/135331922/gitserver-actions-int-conn-cfg-custom-apipath.png?version=1&modificationDate=1642507945571&cacheVersion=1&api=v2&width=680&height=612) |

![](https://bigbrassband.atlassian.net/wiki/download/attachments/135331922/github-mobile.png?version=1&modificationDate=1642507757901&cacheVersion=1&api=v2)

## GitHub.com and GitHub Enterprise examples

|     |
| --- |
| 1.  Lists all repositories (default) |
| ```java<br>/user/repos<br>``` |
| Gets a list of repositories by the authenticated user. This is the same as when no API path is specified. |

|     |
| --- |
| 1.  Display all repositories from <username> |
| ```java<br>/users/<username>/repos<br>``` |
| Gets a list of public repositories for the specified user, **<username>**. <br><br>For example: `/users/johnsmith/repos` |

|     |
| --- |
| 1.  Displays starred repositories |
| ```java<br>/user/starred<br>``` |
| Gets a list of repositories by the authenticated user. This is the same as when no API path is specified. |
| ```java<br>/users/<username>/starred<br>``` |
| Gets the list of starred public/private repositories for the specified user, **<username>**.<br><br>For example: `/users/johnsmith/starred` |

|     |
| --- |
| 1.  List all repositories for the specified organization |
| ```java<br>/orgs/<org>/repos<br>``` |
| Gets a list of repositories for the specified org, **<org>**. _BigBrassBand_<br><br>_**For instance:**_<br><br>```java<br>/orgs/BigBrassBand/repos<br>```<br><br>This will filter for repositories only within the org: `BigBrassBand`. This works for GitHub integrations. |

![](https://bigbrassband.atlassian.net/wiki/download/attachments/135331922/gitlab-mobile.png?version=1&modificationDate=1642507757907&cacheVersion=1&api=v2)

## GitLab.com and GitLab CE|EE examples

|     |
| --- |
| 1.  Lists all projects (default) |
| ```java<br>/api/v4/projects?membership=true<br>``` |
| Gets a list of projects. This is the same as when no API path is specified. |

|     |
| --- |
| 1.  Display all projects from <user\_id> |
| ```java<br>/api/v4/users/<user_id>/projects<br>``` |
| Gets a list of projects for the specified user, **<user\_id>**. _johnsmith_ |

|     |
| --- |
| 1.  Displays starred projects |
| ```java<br>/api/v4/projects?starred=true<br>``` |
| Returns GitLab projects that have been starred by the connecting GitLab user. |

|     |
| --- |
| 1.  Limit to owned projects |
| ```java<br>/api/v4/projects?owned=true<br>``` |
| The current user will be limited to the projects it's explicitly owned. |

|     |
| --- |
| 1.  List projects from within a Group |
| ```java<br>/api/v4/groups/5245789/projects<br>/api/v4/groups/BigBrassBand/projects<br>``` |
| Returns the list of repositories within a GitLab Group (or GitLab Subgroup).<br><br>In the above examples, you can use the **Group id** or your **Group** **name** as query parameter. |

|     |
| --- |
| 1.  List projects from the specified sub-group |
| ```java<br>/api/v4/groups/5245789/projects?include_subgroups=true<br>/api/v4/groups/BigBrassBand/projects?include_subgroups=true<br>``` |
| In the above examples, the `?include_subgroups=true` API extension will return a recursive list of repositories within a nested GitLab Group (or GitLab Subgroup) where the #, `5245789`, is the **Group id**; and `BigBrassBand` is the **Group name**. |


For more information on GitLab custom API paths, see **GitLab API**.

**GitLab version API support:**
Gitlab v9.5 and above -- only API v4
Gitlab v9.0 to v9.4.x -- API v3 and API v4 (_support for API v3 is deprecated_)

**Remember**
The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible. For more information, see [Working with JMESPath filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters).


While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.


_1 Logo owned by_ [_GitLab Inc_](https://gitlab.com/) _used under_ [_license_](https://creativecommons.org/licenses/by-nc-sa/4.0/)