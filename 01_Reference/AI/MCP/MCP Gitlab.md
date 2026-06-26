
## General Link 

> [General Link to MCP Servers documented by code.siemens.com](https://code.siemens.io/ai/opencode/#mcp-servers)

## GitLab MCP (code.siemens.com)

> You will need following environment variables:
> - `GITLAB_OAUTH_CLIENT_ID`
> - `GITLAB_OAUTH_CLIENT_SECRET`

> One possible setup is to create an OAuth application via https://code.siemens.com/-/user_settings/applications:
> 
> 1. Create a new "Application" in your user settings and copy the generated "Application ID" and "Secret"
> 2. Use these values to set `GITLAB_OAUTH_CLIENT_ID` and `GITLAB_OAUTH_CLIENT_SECRET` environment variables on your machine. For Linux/Mac, e.g. add them to your `~/.bashrc` or `~/.zshrc` file, for Windows, set them via System Properties → User Environment Variables.
> 3. Restart your terminal and start opencode via `opencode`. OpenCode will use the provided credentials to authenticate with the GitLab MCP server via OAuth. The first time you run the AI Dev Tool, you will be prompted to authorize the application via your browser.

- [@zereight/mcp-gitlab repository](https://github.com/zereight/gitlab-mcp)
  - [Documentation of the OAuth Setup](https://github.com/zereight/gitlab-mcp/blob/main/docs/auth/oauth-setup.md)

## Example Configuration

Example configurations for the MCP servers can be found in the [[OpenCode]]. Before connecting to an MCP server, make sure to update your configuration file for the respective MCP server you want to connect to.

- [[Claude Code#MCP Configurations]]
- [[GitHub Copilot#MCP Configurations]]
- [[OpenCode#MCP Configurations]]

## Paths

- `C:\Users\z004cj9t\.gitlab-mcp-token.json`
