## MCP Gitlab

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
