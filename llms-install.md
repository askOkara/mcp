# Install Okara MCP

Okara is a hosted remote MCP server. Nothing to install or build, and no API
key to paste. Sign-in is OAuth in the browser.

- Server URL: `https://okara.ai/api/mcp`
- Transport: streamable HTTP
- Auth: OAuth 2.1 with PKCE and dynamic client registration. The client opens
  a browser window to log in to Okara and approve access.
- Requires an Okara account with at least one growth agent: https://okara.ai

## Add it to your client

Claude Code:

    claude mcp add --transport http okara https://okara.ai/api/mcp

Then run `/mcp` in Claude Code and choose Okara to sign in.

Cursor, Cline and other clients that take JSON:

    {
      "mcpServers": {
        "okara": { "url": "https://okara.ai/api/mcp" }
      }
    }

Clients that need an explicit transport: use `streamable-http` (or `http`).

## First use

1. Call `whoami`, then `list_growth_agents` to get an `agentId`.
2. Pass that `agentId` to the other tools.

`whoami`, `list_growth_agents` and `get_credit_balance` are free. Other reads
cost 1 credit. Write tools state their credit cost. Tools that publish, spend
ad money or cancel scheduled posts are marked destructive, and the user must
approve them.

## Troubleshooting

- 401 on first call is expected: it starts the OAuth sign-in.
- Sign-in window does not open: the client needs a local browser. Headless
  environments cannot complete OAuth.
- Tools missing after sign-in: reconnect from the client's MCP panel.
- Help: https://okara.ai/mcp
