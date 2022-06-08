---

title: Commit-msg Hook
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Every developer must have this hook on his local machine in order to:

*   Commit codes locally several times then pushes it to the server.
*   Merge auto-commits with auto-messages without referencing to a Jira ticket.

The commit-msg hook is a python script file and it must be placed in the developer's local repository as: **`.git/hooks/commit-msg`**.  There is no server-side hook required.

The following settings must be configured in the script file:

*   **JIRA\_XMLRPC** \-- path to Jira.

Example: **`https://jira.example.com/rpc/xmlrpc`**

*   **JIRA\_USER**, **JIRA\_PASSWORD** \-- developer's credentials.
*   **JIRA\_TICKET\_PATTERN** \-- pattern that will search ticket references.

Example: **`re.compile(r'\[(\w+7-\d+?)\]')`**

In Linux and OSX, this file must have executable permissions in the file system; in Windows, setting this permission is not necessary.  To use the hook in Windows without python installed, see **[Python on Windows FAQ »](https://docs.python.org/2/faq/windows.html#how-do-i-make-an-executable-from-a-python-script)**.

See the commit-msg hook code on the right panel or download the sample **[commit-msg file ↓](https://bigbrassband.com/files/commit-msg.zip)**, make the necessary changes, and place it in the required folder.



The **commit-msg** hook is a python script file that must be located in the developer's local repository.



**Sample contents of the commit-msg file:**

```py
#!/usr/bin/python
#
# This script is intended to be run as a commit-msg script in a GIT
# repository and check the presence of Jira ticket numbers in the log messages.
#
#    - NO_Jira_TICKET_MESSAGE (an error message returned to the user when the
#      svn commit message doesn't contain a jira ticket);
#    - INVALID_JIRA_TICKET_MESSAGE (an error message returned to the user when
#      the svn commit message contains an invalid jira ticket);
#    - JIRA_XMLRPC (url of the Jira XML-RPC server);
#    - JIRA_USER (name of the Jira user who has permission to look up issues in
#      the Jira server);
#    - JIRA_PASSWORD (password of the Jira user described above);

import sys
import re
import xmlrpclib

NO_JIRA_TICKET_MESSAGE = \
'No Jira ticket present in the commit message. \
Please include the Jira ticket enclosed in brackets: [ABC-789].'
INVALID_JIRA_TICKET_MESSAGE = \
'Proper Jira ticket syntax was found, but none were valid tickets. \
Please check the tickets and try again.'
TOO_MANY_JIRA_TICKETS_MESSAGE = \
'Only 1 Jira ticket is allowed per commit. Please commit only 1 change at a time.'
INVALID_ISSUE_TYPE_MESSAGE = \
'You may not commit against subtasks or task-splits. \
Please commit against the parent ticket.'

JIRA_XMLRPC = 'https://jira.example.com/rpc/xmlrpc'
JIRA_USER = 'user'
JIRA_PASSWORD = 'password'
JIRA_TICKET_PATTERN = re.compile(r'\[(\w+?-\d+?)\]')

FAULT_MSG_ISSUE_NOT_FOUND = 'com.atlassian.jira.rpc.exception.RemotePermissionException'

def check_message(message):
    tickets = JIRA_TICKET_PATTERN.findall(message)

    if not tickets:
        return NO_JIRA_TICKET_MESSAGE

    if len(tickets) > 1:
        return TOO_MANY_JIRA_TICKETS_MESSAGE

    ticket = tickets[0]

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

proxy = xmlrpclib.ServerProxy(JIRA_XMLRPC)

try:
    auth = proxy.jira1.login(JIRA_USER, JIRA_PASSWORD)
except:
    print >> sys.stderr, 'Cannot connect to Jira: ' + str(sys.exc_info()[1])
    sys.exit(2)

msg_file = open(sys.argv[1], 'r')
msg = msg_file.read()

err_msg = check_message(msg)

if err_msg:
    print >> sys.stderr, 'Error: %s\nCommit message:\n%s' % (err_msg, msg)
    sys.exit(1)
```

