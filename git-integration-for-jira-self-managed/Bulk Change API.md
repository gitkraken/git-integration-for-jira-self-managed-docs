---

title: Bulk Change API
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Bulk Change API

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380764495/Bulk+Change+API>

* * *

The bulk change API extends the possibility of importing and exporting repository configuration by automating the process via scripts.

To use the API, users must:

*   install the [**Requests »**](http://docs.python-requests.org/en/latest/user/install/#install) Python package.
    
*   declare `JIRA_BASE`, `JIRA_USER`, and `JIRA_PASSWORD` in the `configuration_conf.py` file.  The `JIRA_USER` defined in this file must have Jira Admin global permissions.  _(Download_ [_**sample file ↓**_](https://bigbrassband.com/files/configuration_conf.zip) _as a zip file.)_
    

HTTP Status code response:

*   **200**  –  success
    
*   **401**  –  user is unauthorized
    
*   **403**  –  lack of privileges _(The user doesn't have Jira Admin global permission)_
    

### Bulk Change REST APIs

*   Page:
    
    [Bulk Export](/wiki/spaces/GIJDC/pages/380797241/Bulk+Export) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Bulk Import](/wiki/spaces/GIJDC/pages/380764507/Bulk+Import) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Get Bulk Import Information](/wiki/spaces/GIJDC/pages/421298278/Get+Bulk+Import+Information) (Git Integration for Jira Data Center)