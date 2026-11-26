# Installing the SportsDataHQ MCP server

SportsDataHQ is a hosted (remote) MCP server over Streamable HTTP. There is nothing to clone, build or run locally.

## 1. Get an API key

Ask the user for their SportsDataHQ API key. If they do not have one, they can create one free (1,000 credits, no card) at https://app.sportsdatahq.com/signup. Connecting and listing tools works without a key; calling a tool needs one.

## 2. Add the server

For Cline, add this to `cline_mcp_settings.json`, replacing YOUR_API_KEY:

```json
{
  "mcpServers": {
    "sportsdatahq": {
      "type": "streamableHttp",
      "url": "https://mcp.sportsdatahq.com/mcp",
      "headers": { "x-api-key": "YOUR_API_KEY" },
      "disabled": false
    }
  }
}
```

If the client cannot send headers, put the key in the URL instead: `https://mcp.sportsdatahq.com/mcp?key=YOUR_API_KEY`.

## 3. Check it works

Call `list_teams`. It costs 1 credit and confirms the key and connection.
