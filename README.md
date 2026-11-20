# Okara MCP

Your AI CMO inside the chat you already use. Okara's hosted MCP server lets
Claude, Cursor, Cline, Gemini and other MCP clients read and operate your
Okara growth agents: strategy and competitors, SEO and GEO audits, Search
Console data, articles, Reddit threads with drafted replies, the X and
LinkedIn content queue, and ads.

- Server URL: `https://okara.ai/api/mcp` (streamable HTTP, OAuth)
- Docs and setup: https://okara.ai/mcp
- Privacy policy: https://okara.ai/privacy
- Account required: https://okara.ai

This repo holds only the client manifests. The server is hosted by Okara.

## Install

Claude Code:

    claude plugin marketplace add askOkara/mcp
    claude plugin install okara@okara

or just `claude mcp add --transport http okara https://okara.ai/api/mcp`.

Cursor: install the plugin from the Cursor marketplace, or add
`https://okara.ai/api/mcp` as a remote MCP server.

Gemini CLI: `gemini extensions install https://github.com/askOkara/mcp`

Cline and others: see [llms-install.md](llms-install.md).

## Credits and safety

Reads cost 1 credit (`whoami`, `list_growth_agents`, `get_credit_balance` are
free). Tools that publish publicly, spend ad budget or cancel scheduled posts
are annotated destructive and require approval.

## License

MIT, see [LICENSE](LICENSE).
