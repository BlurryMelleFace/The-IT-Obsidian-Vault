## MCP Gitlab

```
Use only gitlab. Read-only.

Show my latest merge requests across all projects. List:
- MR title
- project
- source branch → target branch
- state (open/merged/closed)
- created date
- updated date
- assignee and reviewer
```

```
Use only gitlab. Read-only.

List all repositories (projects) under the "Digital Process Plant" group. Show:
- project name
- project ID
- default branch
- last activity date
- visibility
- web URL
```

```
Use only gitlab. Read-only.

Find all open merge requests for the project "siemens/di-pa/sw/dh/ipid/ipid-backend" (adjust path as needed). Show:
- MR title and IID
- author
- source branch → target branch
- labels
- created and updated dates
- pipeline status
- number of approvals
```

## MCP Atlassian

```
Use only mcp-atlassian.

Update Jira issue DPP-6449 description to:

**Goal:**

- Run and test tag identification prototype with 2 SE P&IDs and 2 BASF P&IDs
- Optimize the tag identification if there are any major gaps
- Finalize the result so that it fits end-to-end pipeline
```

```
Show the full details of Jira issue DPP-6449.

Call jira_get_issue with:
- issue_key: "DPP-6449"
- fields: summary,status,issuetype,project,assignee,reporter,description,labels,created,updated,priority,parent
- comment_limit: 20
```

```
Use only mcp-atlassian. Read-only.

Find the Jira agile board named exactly "IPID Value Stream Crew". Show:
- board name
- board id
- board type
- backing Jira project key and project name
- total number of issues on the board
- the 20 most recently updated issues on that board
```
