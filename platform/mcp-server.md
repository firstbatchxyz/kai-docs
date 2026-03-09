# MCP Server

Kai exposes a [Model Context Protocol](https://modelcontextprotocol.io) (MCP) server that gives AI assistants and development tools direct access to Kai's capabilities. Connect your IDE, agent framework, or custom tooling to scan code, manage vulnerabilities, run evolutions, and more — all through a standardized protocol.

## Server URL

```
https://production.kai-backend.dria.co/mcp
```

## Authentication

The MCP server uses OAuth 2.1 with PKCE for secure authentication. When you connect an MCP client, the server handles the authorization flow automatically:

1. Your MCP client initiates a connection to the server URL
2. The OAuth flow redirects you to sign in with GitHub
3. A JWT token is issued and used for subsequent requests
4. Sessions are managed server-side with automatic cleanup

Most MCP clients (Claude Desktop, VS Code Copilot, Cursor, etc.) handle this flow transparently — you just approve the GitHub authorization when prompted.

## Available Tools

The MCP server exposes 29 tools across 8 categories. Each tool maps to a Kai API endpoint and returns structured results.

### Workspaces

| Tool | Description |
|------|-------------|
| `workspaces_list` | List all workspaces you're a member of |
| `workspaces_view` | Get details and integrations for a specific workspace |

### Repositories

| Tool | Description |
|------|-------------|
| `repos_list` | List all repositories in a workspace |
| `repos_view` | Get details of a specific repository |
| `repos_add_github` | Add a GitHub repository to a workspace |
| `repos_delete` | Delete a repository from a workspace |
| `repos_file_tree` | Get the file tree of a GitHub repository |
| `repos_file_contents` | Get the contents of one or more files (comma-separated paths) |

### Scans

| Tool | Description |
|------|-------------|
| `scans_list` | List all security scans for a repository |
| `scans_start` | Start a new security scan (use `scans_tiers` first to get tier IDs) |
| `scans_view` | Get details and status of a specific scan |
| `scans_abort` | Abort a running scan |
| `scans_status_updates` | Get real-time status updates and agent iteration logs |
| `scans_tiers` | Get available scan tiers and their agent configurations |

### Exploits

| Tool | Description |
|------|-------------|
| `exploits_list` | List all vulnerability findings from a scan, with severity and status |
| `exploits_view` | Get detailed exploit information including hypothesis, verification, and fixes |

### Evolutions

| Tool | Description |
|------|-------------|
| `evolutions_list` | List all evolution tasks for a repository |
| `evolutions_start` | Start a new evolutionary code optimization task |
| `evolutions_view` | Get details, status, and progress of an evolution task |
| `evolutions_abort` | Abort a running evolution |
| `evolutions_iterations` | Get iteration history for an evolution task |
| `evolutions_programs` | Get the generated programs from an evolution task |

### Evaluators

| Tool | Description |
|------|-------------|
| `evaluators_list` | List all evaluators for a repository |
| `evaluators_view` | Get details of a specific evaluator |
| `evaluators_generate_start` | Start LLM-based evaluator generation for specified code scopes |

### Integrations

| Tool | Description |
|------|-------------|
| `integrations_github_issue` | Create a GitHub issue for a specific exploit |
| `integrations_jira_issue` | Create a Jira issue for a specific exploit |

### Billing

| Tool | Description |
|------|-------------|
| `billing_credits` | Get the current credit balance for a workspace |
| `billing_transactions` | Get transaction history (usage, renewals) for a workspace |

## Connecting Your MCP Client

### Claude Desktop

Add the following to your Claude Desktop MCP configuration:

```json
{
  "mcpServers": {
    "kai": {
      "url": "https://production.kai-backend.dria.co/mcp"
    }
  }
}
```

### Cursor / VS Code

Add the MCP server URL in your editor's MCP settings. The OAuth flow will prompt you to authorize with GitHub on first connection.

### Custom Clients

Any MCP-compatible client can connect using the server URL. The server supports SSE (Server-Sent Events) transport and follows the MCP specification for tool discovery and invocation.

## Example Workflows

### Run a Security Scan

```
1. workspaces_list → get your workspace ID
2. repos_list → find the repository
3. scans_tiers → check available scan tiers
4. scans_start → kick off the scan
5. scans_view → monitor progress
6. exploits_list → review findings when complete
```

### Create Issues from Findings

```
1. exploits_list → get exploits from a completed scan
2. exploits_view → review a specific finding
3. integrations_github_issue → create a GitHub issue
```

### Start an Evolution

```
1. repos_list → find the target repository
2. evolutions_start → begin the evolution task
3. evolutions_view → monitor progress
4. evolutions_programs → review generated solutions
```

## Next Steps

- [Kai Evolve](../kai-evolve/overview) — Learn about evolutionary code optimization
- [Integrations](integrations) — Connect GitHub and Linear for issue tracking
- [Security Reports](../kai-security/reports) — Generate audit reports from scan results
