# Installing the CourtsApp MCP server (for AI agents)

CourtsApp is a hosted remote MCP server. There is nothing to clone, build or install, and no API key.

- **URL:** `https://api.courtsapp.com/mcp`
- **Transport:** Streamable HTTP
- **Auth:** none

## Cline

1. Find Cline's MCP settings file, `cline_mcp_settings.json`.
   - Cline CLI: `~/.cline/data/settings/cline_mcp_settings.json` (or `<data-dir>/settings/cline_mcp_settings.json` if `--data-dir` is set).
   - VS Code extension: open **MCP Servers → Configure** to open the file.
2. Add this entry under `mcpServers`. Keep any servers already there.

```json
"courtsapp": {
  "type": "streamableHttp",
  "url": "https://api.courtsapp.com/mcp",
  "disabled": false,
  "autoApprove": []
}
```

3. Start a new task. The tools show up as `search_courts`, `get_facility_times` and the rest.

## Check it works

Ask: "Find a pickleball court near Plainville, CT tomorrow around 6pm." The agent should call `search_courts` and return clubs with open times, prices and booking links.

## Other clients

Any MCP client that supports remote servers: add a Streamable HTTP server with the URL above and no headers.
