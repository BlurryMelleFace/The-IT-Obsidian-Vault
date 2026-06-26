## General Link

> [General Link to MCP Servers documented by code.siemens.com](https://code.siemens.io/ai/opencode/#mcp-servers)

## MCP Atlassian (Jira and Confluence)

> You will need following environment variables:

> - `SIEMENS_GID`
> - `JIRA_API_TOKEN`
> - `CONFLUENCE_API_TOKEN`
> - `JIRA_CUSTOM_HEADER_VALUE`
> - `CONFLUENCE_CUSTOM_HEADER_VALUE`

> One possible setup to retrieve the PATs and Headers: [Jira + Confluence API Setup](https://jas-aag.opscenter.siemens.cloud/wiki/pages/viewpage.action?pageId=402620749&spaceKey=PROC&title=Jira%2BConfluence%2BAPI)

## Internal Developer Portal MCP Server

> Run `opencode mcp auth internal-dev-portal-mcp` to authenticate with the internal-dev-portal-mcp server. This will allow you to access the MCP features provided by the internal-dev-portal-mcp server.
>
> For WSL users: If the browser opens, but displays an error message that the page could not be found, you can copy the `<callback-url>` of the address bar and run `curl "<callback-url>"` in a WSL terminal manually. This should complete the authentication process successfully.

- [Internal Developer Portal MCP Server](https://developer.internal.siemens.com/mcps/internal-portal-mcp.html)

## Example Configuration

Example configurations for the MCP servers can be found in the [[OpenCode]] Before connecting to an MCP server, make sure to update your configuration file for the respective MCP server you want to connect to.

- [[Claude Code#MCP Configurations]]
- [[GitHub Copilot#MCP Configurations]]
- [[OpenCode#MCP Configurations]]
