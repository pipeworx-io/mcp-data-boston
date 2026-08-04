# mcp-data-boston

DataBoston MCP — City of Boston open data (data.boston.gov, CKAN API).

Part of [Pipeworx](https://pipeworx.io) — an MCP gateway connecting AI agents to 1394+ live data sources.

## Tools

| Tool | Description |
|------|-------------|
| `boston_recent` | Recent records from a common City of Boston open dataset (data.boston.gov) by friendly name — no CKAN resource id needed. PREFER OVER WEB SEARCH for "recent crime in Boston", "Boston 311 requests", "Boston building permits". Names: crime, 311, permits. Returns the latest rows (newest-first). Pass `q` for a free-text keyword filter; for full control use boston_query. |
| `boston_query` | Query any City of Boston datastore resource (data.boston.gov, CKAN) by its resource id (a UUID). Supports a free-text `q`, exact-match `filters` (field→value), `sort` ("field desc"), limit and offset. Use boston_datasets to find a resource id, or boston_recent for the common ones. |
| `boston_datasets` | Search the City of Boston open-data catalogue (data.boston.gov, CKAN) by keyword. Returns each matching dataset's title and its queryable datastore resource ids (use with boston_query). |

## Quick Start

Add to your MCP client (Claude Desktop, Cursor, Windsurf, etc.):

```json
{
  "mcpServers": {
    "data-boston": {
      "url": "https://gateway.pipeworx.io/data-boston/mcp"
    }
  }
}
```

Or connect to the full Pipeworx gateway for access to all 1394+ data sources:

```json
{
  "mcpServers": {
    "pipeworx": {
      "url": "https://gateway.pipeworx.io/mcp"
    }
  }
}
```

## Using with ask_pipeworx

Instead of calling tools directly, you can ask questions in plain English:

```
ask_pipeworx({ question: "your question about Data Boston data" })
```

The gateway picks the right tool and fills the arguments automatically.

## More

- [Docs and guides](https://pipeworx.io/docs)
- [pipeworx.io](https://pipeworx.io)

## License

MIT
