---

title: Branches API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Branches REST API will obtain list of branches associated to a Jira issue.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        There are two types of users who can perform the Branches API call:
        <ol style='margin-bottom:-10px'>
            <li>Jira <b>administrators</b></li>
            <li>Jira user who has <b>all</b> of the following:
            <ol type='a'>
                <li><b>View/browse permissions</b> to the project;</li>
                <li><b>View Development Tools permissions</b> to the same project; and</li>
                <li>The repository is <b>associated</b> to the project.</li>
            </ol>
            </li>
        </ol>
    </div>
    </div>
</div>

&nbsp;

## Gets a set of branches from Jira issue based on the associated commit links

### Url
`{JiraBaseURL}/rest/gitplugin/1.0/issues/branches?key={issuekey}`

### Method
GET

### Parameters

| Field | Description |
| :--- | :--- |
| _**issueKey**_ | _String_. Optional.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TEST-435`. |

### Response

If the _optional query_ is not defined, it will return ALL indexed git branches. For example: `{JiraBaseURL}/rest/gitplugin/1.0/issues/branches`

### Example

`http://jira.yourorg.com/rest/gitplugin/1.0/issues/branches?key=TEST-435`

```json
Result:
{
    "success":true,
    "branches":["master","release","TEST-435"]
}
```

&nbsp;

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If there are no commits associated with the specified task (ISSUE_KEY), no branches are going to be displayed for this request.
    </div>
    </div>
</div>

&nbsp;

## Get the list of branches bound to an issue

A different request is used to retrieve branches on the “issue” page. It includes branches whose name is associated with the issue key.

### Url
`{JIRA_BASE_URL}/rest/gitplugin/1.0/issuegitdetails/issue/{ISSUE_KEY}`


### Method
GET

### Parameters

| Field | Description |
| :--- | :--- |
| _**issueKey**_ | _String_. Optional.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TEST-435`. |

### Response

It includes branches whose name is associated with the issue. The result will show the branches on which commits exist in the specified Jira issue. It's a set of branches to which the commits are bound to the issue they are associated with. They can be viewed in the the Git Commits tab.

### Example

`https://jira.yourorg.com/rest/gitplugin/1.0/issuegitdetails/issue/TEST-435`

```json
Result:
{
    "commitCount": 53,
    "repositories":[
        {
            "repoId": 12718,
            "repoName": "test-repo",
            "isGitViewerEnabled": true,
            "isRepoApiEnabled": true,
            "branches":[
                {
                    "name": "TEST-435-branch-001",
                    "gkBranchUrl": "gitkraken://repolink/d5407d...4a03c/branch/TEST-435-branch-001?url=https%3A%2F%2Fgithub.com%2FWilyCoyote%2Ftest-repo.git",
                    "glBranchUrl": "vscode://eamodio.gitlens/link/r/d5407d...4a03c/b/TEST-435-branch-001?url=https%3A%2F%2Fgithub.com%2FWilyCoyote%2Ftest-repo.git",
                    "isAheadBehindPresented": true,
                    "ahead": 2,
                    "behind": 6448,
                    "externalUrl": "https://github.com/WilyCoyote/test-repo/tree/TEST-435-branch-001"
                },
                {
                    "name": "TEST-435-branch-002",
                    "gkBranchUrl": "gitkraken://repolink/d5407d...4a03c/branch/TEST-435-branch-002?url=https%3A%2F%2Fgithub.com%2FWilyCoyote%2Ftest-repo.git",
                    "glBranchUrl": "vscode://eamodio.gitlens/link/r/d5407d...4a03c/b/GIT-4932?url=https%3A%2F%2Fgithub.com%2FWilyCoyote%2Ftest-repo.git",
                    "isAheadBehindPresented": true,
                    "ahead": 0,
                    "behind": 6379,
                    "externalUrl": "https://github.com/WilyCoyote/test-repo/tree/TEST-435-branch-002"
                }
            ]
        }
    ],
    "enableBranchCreation": true,
    "gkEnabled": true,
    "glEnabled": true,
    "notAllPermissions": false
}
```

&nbsp;

### I made the correct request but I don't see the expected branches in the results?

If the issue displays these branches while the request does not, the likely explanation is that, the request is being executed by a user who lacks sufficient permissions to access the repository. (See the yellow infobox above.)

For a quick check, it is possible to omit the issue key in the request.

It will look like this: `https://jira.your-org.com/rest/gitplugin/1.0/issues/branches`

When a user is granted specific permissions, they will receive a json response that shows various branches.

&nbsp;
<hr>
&nbsp;


**[« Back to: REST API index](/git-integration-for-jira-data-center/rest-api-gij-self-managed)**

