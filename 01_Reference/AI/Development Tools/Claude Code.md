[Managed Claude Code Repository](https://code.siemens.com/dev-boost/managed-claude-code/-/raw/main/README.md?ref_type=heads)

Clone the Repo and let copilot do the installation
## Prerequisites

- Create [SDC Profile](https://sdc.siemens.cloud/profile/general) and obtain [SDC LLM Gateway credentials](https://sdc.siemens.cloud/profile/subscriptions)
- Generate a [personal access token](https://code.siemens.com/-/user_settings/personal_access_tokens?scopes=read_user,read_repository&name=claude-code-scan&description=https://dev-boost.code.siemens.io/managed-claude-code/) on code.siemens.com with `read_user` and `read_repository` scopes
- On Windows, Claude Code requires `git-bash`. Set `CLAUDE_CODE_GIT_BASH_PATH=C:\Program Files\Git\bin\bash.exe` if not in `PATH`

## Installation

### Linux / macOS / WSL

```sh
export ANTHROPIC_API_KEY="12345..."
export CODE_SCAN_TOKEN="CSC-glpat-..."
curl -fsSL https://claude.ai/install.sh | bash
curl -fsSL https://dev-boost.code.siemens.io/managed-claude-code/post-install.sh | sh
```

### Windows (PowerShell)

```powershell
$env:ANTHROPIC_API_KEY = "12345..."
$env:CODE_SCAN_TOKEN = "CSC-glpat-..."
irm https://claude.ai/install.ps1 | iex
irm https://dev-boost.code.siemens.io/managed-claude-code/post-install.ps1 | iex
```

Then run `claude`. For API key selection, choose "Yes".

## Environment Variables

```bash
export ANTHROPIC_BASE_URL="https://llm.sdc.siemens.cloud"
export ANTHROPIC_API_KEY="***"
export CLAUDE_CODE_DISABLE_EXPERIMENTAL_BETAS="1"
export ANTHROPIC_MODEL="claude-sonnet-4-6@default"
```

## Model Selection

Set your preferred models in `~/.claude/settings.json`:

```json
"env": {
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "claude-opus-4-6@default",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "claude-sonnet-4-6@default",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "claude-haiku-4-5-20251001"
}
```

Use `/model` in Claude Code to switch between models. Available models: [SDC documentation](https://sdc.siemens.cloud/products/sdc-llm-gateway).

## Secrets

| Secret Name         | Description                                       | Required |
| ------------------- | ------------------------------------------------- | -------- |
| `ANTHROPIC_API_KEY` | API key for SDC LLM Gateway                       | Yes      |
| `CODE_SCAN_TOKEN`   | PAT from code.siemens.com for GenAI-CodeScan Hook | Yes      |


## MCP Configurations

- [[MCP Atlassian]]
- [[MCP Gitlab]]

## Path

- `C:\Users\z004cj9t\.mcp.json`

```json
{
  "mcpServers": {
    "gitlab-csc": {
      "command": "npx",
      "args": [
        "--registry",
        "https://registry.npmjs.org",
        "-y",
        "@zereight/mcp-gitlab@latest"
      ],
      "env": {
        "GITLAB_USE_OAUTH": "true",
        "GITLAB_OAUTH_CLIENT_ID": "${GITLAB_OAUTH_CLIENT_ID}",
        "GITLAB_OAUTH_CLIENT_SECRET": "${GITLAB_OAUTH_CLIENT_SECRET}",
        "GITLAB_OAUTH_REDIRECT_URI": "http://127.0.0.1:8888/callback",
        "GITLAB_API_URL": "https://code.siemens.com/api/v4",
        "GITLAB_READ_ONLY_MODE": "false",
        "USE_PIPELINE": "true"
      }
    },
    "mcp-atlassian": {
      "type": "stdio",
      "command": "uvx",
      "args": ["mcp-atlassian"],
      "env": {
        "JIRA_URL": "https://jas-aag.opscenter.siemens.cloud/jira/",
        "JIRA_USERNAME": "${SIEMENS_GID}",
        "JIRA_PERSONAL_TOKEN": "${JIRA_PAT}",
        "JIRA_CUSTOM_HEADERS":
          "x-cloud-operations-api=${JIRA_CUSTOM_HEADER_VALUE}",
        "CONFLUENCE_URL": "https://jas-aag.opscenter.siemens.cloud/wiki/",
        "CONFLUENCE_USERNAME": "${SIEMENS_GID}",
        "CONFLUENCE_API_TOKEN": "${CONFLUENCE_PAT}",
        "CONFLUENCE_CUSTOM_HEADERS":
          "x-cloud-operations-api=${CONFLUENCE_CUSTOM_HEADER_VALUE}"
      }
    },
    "internal-dev-portal-mcp": {
      "command": "npx",
      "args": [
        "--registry",
        "https://registry.npmjs.org",
        "-y",
        "mcp-remote@latest",
        "https://mcp.fds.siemens.cloud/mcp"
      ]
    }
  }
}
```