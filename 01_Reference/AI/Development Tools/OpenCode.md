[OpenCode](https://opencode.ai/en)
## Installation

Install via the [official installation documentation](https://opencode.ai/docs#install).
There are different installation instructions for Linux, Mac and Windows.

> INFO: For Windows, it is recommended to use the Windows Subsystem for Linux (WSL) to run OpenCode and run the official installation script via `curl -fsSL https://opencode.ai/install | bash`. Another option is the installation via `npm i -g opencode-ai`.

## Run OpenCode

- Via the [TUI](https://opencode.ai/docs/tui/): `opencode`
- Via the [Web UI](https://opencode.ai/docs/web/): `opencode web`
  > INFO: This will start a local web server and open the web UI in your default browser.
- Via the [CLI](https://opencode.ai/docs/cli/): `opencode run ...`
- Via an [IDE](https://opencode.ai/docs/ide/)

## Connect to a Provider

- [Connect OpenCode to GitHub Copilot](https://opencode.ai/docs/providers/#github-copilot)
  > INFO: Start opencode via the console with `opencode`
  >
  > -> Enter `/connect` and search for `GitHub Enterprise` -> Enter `https://siemens.ghe.com` as provider
  >
  > -> Open <https://github.siemens.cloud/login/device/> to enter the device code displayed via opencode to finish establishing the connection to GitHub Copilot

## MCP Configurations

- [[MCP Atlassian]]
- [[MCP Gitlab]]

## Path

- `C:\Users\z004cj9t\.config\opencode\opencode.jsonc`

```json
{
  "$schema": "https://opencode.ai/config.json",
  "autoupdate": true,
  "share": "disabled",
  "disabled_providers": ["opencode", "openai"],
  "model": "github-copilot/gpt-5.5",
  "small_model": "github-copilot/claude-haiku-4.5",
  "default_agent": "plan",
  "agent": {
    "plan": {
      "model": "github-copilot/gpt-5.5"
    },
    "build": {
      "model": "github-copilot/gpt-5.5"
    },
    "code-reviewer": {
      "description": "Reviews code for best practices and potential issues",
      "model": "github-copilot/gpt-5.5",
      "prompt": "You are a code reviewer. Focus on security, performance, and maintainability.",
      "tools": {
        "write": false,
        "edit": false
      }
    }
  },
  "provider": {
    "siemens": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "code.siemens.com",
      "options": {
        "baseURL": "https://api.siemens.com/llm/v1"
      },
      "models": {
        "deepseek-v4-flash": {
          "limit": {
            "context": 202752,
            "output": 202752
          }
        },
        "qwen-3.6-27b": {
          "limit": {
            "context": 262144,
            "output": 262144
          },
          "modalities": {
            "input": ["text", "image"],
            "output": ["text"]
          }
        },
        "ministral-3-14b-instruct-2512": {
          "limit": {
            "context": 256000,
            "output": 256000
          },
          "modalities": {
            "input": ["text", "image"],
            "output": ["text"]
          }
        }
      }
    }
  },
  "mcp": {
    "gitlab-csc": {
      "type": "local",
      "enabled": true,
      "timeout": 120000,
      "command": [
        "npx",
        "--registry",
        "https://registry.npmjs.org",
        "-y",
        "@zereight/mcp-gitlab@latest"
      ],
      "environment": {
        "GITLAB_USE_OAUTH": "true",
        "GITLAB_OAUTH_CLIENT_ID": "{env:GITLAB_OAUTH_CLIENT_ID}",
        "GITLAB_OAUTH_CLIENT_SECRET": "{env:GITLAB_OAUTH_CLIENT_SECRET}",
        "GITLAB_OAUTH_REDIRECT_URI": "http://127.0.0.1:8888/callback",
        "GITLAB_API_URL": "https://code.siemens.com/api/v4",
        "GITLAB_READ_ONLY_MODE": "false",
        "USE_PIPELINE": "true"
      }
    },
    "mcp-atlassian": {
      "type": "local",
      "enabled": true,
      "timeout": 120000,
      "command": ["uvx", "mcp-atlassian"],
      "environment": {
        "JIRA_URL": "https://jas-aag.opscenter.siemens.cloud/jira/",
        "JIRA_USERNAME": "{env:SIEMENS_GID}",
        "JIRA_PERSONAL_TOKEN": "{env:JIRA_PAT}",
        "JIRA_CUSTOM_HEADERS":
          "x-cloud-operations-api={env:JIRA_CUSTOM_HEADER_VALUE}",
        "CONFLUENCE_URL": "https://jas-aag.opscenter.siemens.cloud/wiki/",
        "CONFLUENCE_USERNAME": "{env:SIEMENS_GID}",
        "CONFLUENCE_API_TOKEN": "{env:CONFLUENCE_PAT}",
        "CONFLUENCE_CUSTOM_HEADERS":
          "x-cloud-operations-api={env:CONFLUENCE_CUSTOM_HEADER_VALUE}"
      }
    },
    "internal-dev-portal-mcp": {
      "type": "local",
      "enabled": true,
      "timeout": 120000,
      "command": [
        "npx",
        "--registry",
        "https://registry.npmjs.org",
        "-y",
        "mcp-remote@latest",
        "https://mcp.fds.siemens.cloud/mcp"
      ]
    }
  },
  "permission": {
    "read": {
      "*": "allow",
      "*.env": "deny",
      "*.env.*": "deny",
      "*.env.example": "allow"
    },

    "external_directory": {
      "~/go/pkg/mod/**": "allow"
    },
    "edit": {
      "~/go/pkg/mod/**": "deny"
    },

    "gitlab-csc_*": "ask",
    "gitlab-csc_get_*": "allow",
    "gitlab-csc_list_*": "allow",
    "gitlab-csc_search_*": "allow",
    "gitlab-csc_download_*": "allow",
    "gitlab-csc_validate_*": "allow",
    "gitlab-csc_verify_*": "allow",
    "gitlab-csc_discover_tools": "allow",
    "gitlab-csc_health_check": "allow",
    "gitlab-csc_mr_discussions": "allow",
    "gitlab-csc_my_issues": "allow",
    "gitlab-csc_whoami": "allow",

    "mcp-atlassian_*": "ask",
    "mcp-atlassian_jira_search*": "allow",
    "mcp-atlassian_jira_get_*": "allow",
    "mcp-atlassian_jira_batch_get_*": "allow",
    "mcp-atlassian_jira_download_*": "allow",
    "mcp-atlassian_confluence_search*": "allow",
    "mcp-atlassian_confluence_get_*": "allow",
    "mcp-atlassian_confluence_download_*": "allow",

    "internal-dev-portal-mcp_*": "ask",
    "internal-dev-portal-mcp_backstage*": "allow",
    "internal-dev-portal-mcp_search*": "allow",
    "internal-dev-portal-mcp_generateCatalogInfo": "allow"
  }
}
```



