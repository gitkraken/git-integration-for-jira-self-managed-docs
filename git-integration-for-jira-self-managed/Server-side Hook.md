---

title: Server-side Hook
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Server-side Hook

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/91980350/Server-side+Hook>

* * *

In addition to the commit-msg hook, you can use server-side hooks to apply policies for your project.  The server runs these scripts before and after the push.  The server-side hook, like commit-msg hook, requires Python to be installed.

In Linux and OSX, hook scripts must have executable permissions in the file system.

For information about the local hook that should be installed, see **[Customizing Git – Hooks »](http://git-scm.com/book/ch7-3.html "Customizing Git: Git Hooks")**.  For further information about git hooks, see **[githooks.com »](http://githooks.com/)**.

When the server handles the push from a client, the **pre-receive** script is run first.  When commits does not have proper Jira issue tagging, an error message from client to server is raised.

The **pre-receive** server-side hook requires git administrators to:

1.  Copy the **pre-receive** script file from the `hooks/` folder in the git repository to the Git server repository `hooks/` folder.
2.  Configure **JIRA\_XMLRPC**, **JIRA\_USER**, **JIRA\_PASSWORD** and **PROJECT\_KEYS** in the pre-receive file.

  

The PROJECT\_KEYS setting defines an array of project keys which is compared to a ticket key from the commit message.  When Jira is not available, the hook simply checks the commit message if it contains the string pattern satisfying its declared conditions.

**Pattern example:**  
**`(PROJECT_KEY1|PROJECT_KEY2|...)-\d+`**

  

The PROJECT\_KEYS variable is only used when Jira is not available, otherwise, this setting in the **pre-receive** file is ignored. The hook will not perform any checks if the PROJECT\_KEY array is empty and Jira is not available.

  

See the server-side hook script on the right panel or download the sample **[pre-receive file ↓](https://bigbrassband.com/files/pre-receive.zip)** – make the necessary changes, and place it in the required folder.

  

The server-side hook script enforces users to include correct Jira tags.

  

**Sample contents of the pre-receive file:**

```py
#!/usr/bin/python
import sys
import os
import xmlrpclib
import subprocess
import sys
import re

JIRA_XMLRPC = 'https://jira.example.com/rpc/xmlrpc'
JIRA_USER = 'user'
JIRA_PASSWORD = 'password'

PROJECT_KEYS = ['EXAMPLE', 'EXAMPLE']

NO_JIRA_TICKET_MESSAGE = \
'No Jira ticket present in the commit message. \
Please include the Jira ticket key.'
INVALID_JIRA_TICKET_MESSAGE = \
'Proper Jira ticket syntax was found, but none were valid tickets. \
Please check the tickets and try again.'
INVALID_ISSUE_TYPE_MESSAGE = \
'You may not commit against subtasks or task-splits. \
Please commit against the parent ticket.'

FAULT_MSG_ISSUE_NOT_FOUND = 'com.atlassian.jira.rpc.exception.RemotePermissionException'

proxy = xmlrpclib.ServerProxy(JIRA_XMLRPC)

def git(args, **kwargs):
    environ = os.environ.copy()
    if 'repo' in kwargs:
        environ['GIT_DIR'] = kwargs['repo']
    if 'work' in kwargs:
        environ['GIT_WORK_TREE'] = kwargs['work']
    proc = subprocess.Popen(args, stdout=subprocess.PIPE, env=environ)
    return proc.communicate()

def get_log(a, b, **kw):
    entries = {}
    (results, code) = git(('git', 'log', '--pretty=oneline', "%s..%s" % (a, b)), **kw)
    lines = results.splitlines()
    for line in lines:
        (commit, msg)=line.split(' ', 1)
        entries[commit] = msg

    return entries

def check_message(auth, message, ticket_re_pattern):
    tickets = ticket_re_pattern.findall(message)

    if not tickets:
        return NO_JIRA_TICKET_MESSAGE

    if auth == None:
        return None

    for ticket in tickets:
        try:
            issue = proxy.jira1.getIssue(auth, ticket)
        except xmlrpclib.Fault, e:
            if e.faultString.find(FAULT_MSG_ISSUE_NOT_FOUND) >= 0:
                return INVALID_JIRA_TICKET_MESSAGE
            else:
                raise

    # Check if issue is subtask or task-split
    if issue['type'] == '8' or issue['type'] == '5':
        return INVALID_ISSUE_TYPE_MESSAGE

    return None

def build_ticket_re(auth):
    projects = proxy.jira1.getProjectsNoSchemes(auth)
    return build_ticket_re_for_project_list(map(lambda project: project['key'], projects));

def build_ticket_re_for_project_list(projects):
    pattern_string = '\\b('
    for idx, project in enumerate(projects):
        if (idx>0):
            pattern_string +='|'
        pattern_string +=project
        pattern_string +='-\d+?'

    pattern_string +=')\\b';

    return re.compile(pattern_string)

def login():
    try:
        auth = proxy.jira1.login(JIRA_USER, JIRA_PASSWORD)
    except:
        print >> sys.stderr, 'Cannot connect to Jira: ' + str(sys.exc_info()[1])
        sys.exit(2)

    return auth

try:
    auth = login()
    isAuthenticated = True
except:
    isAuthenticated = False

if isAuthenticated:
    ticket_re_pattern = build_ticket_re(auth)
else:
    ticket_re_pattern = build_ticket_re_for_project_list(PROJECT_KEYS);

repo = os.getcwd()
basedir = os.path.join(repo, "..")

line = sys.stdin.read()
(base, commit, ref) = line.strip().split()
commits = get_log(base, commit)

for c, msg in commits.iteritems():
    err_msg = check_message(auth if isAuthenticated else None, msg, ticket_re_pattern)

    if err_msg:
        print >> sys.stderr, 'Error: %s\nCommit message:\n%s' % (err_msg, msg)
        print >> sys.stderr, 'Install pre-commit hook (https://bigbrassband.com/api-doc.html#cmhook) to run this check at the commit time'
        sys.exit(1)
```

  

## Related articles

*   Page:
    
    [Webhooks](/wiki/spaces/GIJDC/pages/94142715/Webhooks)
    
*   Page:
    
    [Hooks and Webhooks](/wiki/spaces/GIJDC/pages/94208056/Hooks+and+Webhooks)
    
*   Page:
    
    [Jira Workflow Hook](/wiki/spaces/GIJDC/pages/94142710/Jira+Workflow+Hook)
    
*   Page:
    
    [Server-side Hook](/wiki/spaces/GIJDC/pages/91980350/Server-side+Hook)
    
*   Page:
    
    [Commit-msg Hook](/wiki/spaces/GIJDC/pages/92209994/Commit-msg+Hook)