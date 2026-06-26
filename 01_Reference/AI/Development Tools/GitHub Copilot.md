## MCP Configurations

- [[MCP Atlassian]]
- [[MCP Gitlab]]

### Path

`C:\Users\z004cj9t\AppData\Roaming\Code\User\mcp.json`

### Configuration

```json
{
    "servers": {
        "gitlab-csc": {
            "command": "npx",
            "args": ["--registry", "https://registry.npmjs.org", "-y", "@zereight/mcp-gitlab@latest"],
            "env": {
                "GITLAB_USE_OAUTH": "true",
                "GITLAB_OAUTH_CLIENT_ID": "${env:GITLAB_OAUTH_CLIENT_ID}",
                "GITLAB_OAUTH_CLIENT_SECRET": "${env:GITLAB_OAUTH_CLIENT_SECRET}",
                "GITLAB_OAUTH_REDIRECT_URI": "http://127.0.0.1:8888/callback",
                "GITLAB_API_URL": "https://code.siemens.com/api/v4",
                "GITLAB_READ_ONLY_MODE": "false",
                "USE_PIPELINE": "true"
            }
        },
        "mcp-atlassian": {
            "command": "uvx",
            "args": ["mcp-atlassian"],
            "env": {
                "JIRA_URL": "https://jas-aag.opscenter.siemens.cloud/jira/",
                "JIRA_USERNAME": "${env:SIEMENS_GID}",
                "JIRA_PERSONAL_TOKEN": "${env:JIRA_PAT}",
                "JIRA_CUSTOM_HEADERS": "x-cloud-operations-api=${env:JIRA_CUSTOM_HEADER_VALUE}",
                "CONFLUENCE_URL": "https://jas-aag.opscenter.siemens.cloud/wiki/",
                "CONFLUENCE_USERNAME": "${env:SIEMENS_GID}",
                "CONFLUENCE_API_TOKEN": "${env:CONFLUENCE_PAT}",
                "CONFLUENCE_CUSTOM_HEADERS": "x-cloud-operations-api=${env:CONFLUENCE_CUSTOM_HEADER_VALUE}"
            }
        },
        "internal-dev-portal-mcp": {
            "command": "npx",
            "args": ["--registry", "https://registry.npmjs.org", "-y", "mcp-remote@latest", "https://mcp.fds.siemens.cloud/mcp"]
        }
    }
}
```
