# SportsDataHQ MCP server

[![SportsDataHQ MCP connector](https://glama.ai/mcp/connectors/io.github.noahowsh/sportsdatahq/badges/score.svg)](https://glama.ai/mcp/connectors/io.github.noahowsh/sportsdatahq)

One API key for nine sports. Stats, play-by-play, sportsbook odds and player props for the NHL, NFL, NBA, MLB, 17 soccer leagues, ATP and WTA tennis, five golf tours, the UFC and cricket, as a hosted MCP server for Claude, ChatGPT, Cursor or any MCP client, and a REST API for your code.

**Server:** `https://mcp.sportsdatahq.com/mcp`. One connector covers every sport: it finds the right tool for a question and runs it. For one sport's tools directly, add the sport to the path, for example `https://mcp.sportsdatahq.com/mcp/nba`.

**Key:** free, 1,000 credits a month, no card: [create an account](https://app.sportsdatahq.com/signup?utm_source=github&utm_medium=readme&utm_campaign=sportsdatahq-mcp). Claude and ChatGPT ask you to sign in on the first call; other clients pass the key as an `x-api-key` header or `?key=`.

## Connect

Claude Code:

```
claude mcp add --transport http sportsdatahq https://mcp.sportsdatahq.com/mcp
```

Cursor, VS Code, Claude Desktop and other clients:

```json
{ "mcpServers": { "sportsdatahq": { "url": "https://mcp.sportsdatahq.com/mcp?key=YOUR_API_KEY" } } }
```

REST: `POST https://api.sportsdatahq.com/v1/<sport>/<tool>` with your key in the `x-api-key` header. `GET https://api.sportsdatahq.com/v1/sports` lists the sports.

## What's in it

The same tools, data and credit costs as each sport's own API ([PuckAPI](https://puckapi.com), [EndzoneAPI](https://endzoneapi.com), [DunkAPI](https://dunkapi.com), [FastballAPI](https://fastballapi.com), [StrikerAPI](https://strikerapi.com), [AcesAPI](https://acesapi.com), [BirdieAPI](https://birdieapi.com), [FighterAPI](https://fighterapi.com), [YorkerAPI](https://yorkerapi.com)), where each tool's reference lives. A call costs 1 to 25 credits. Plans: Pro $79/mo (50,000 credits), Scale $199 (150,000), Business $399 (400,000), Enterprise $799 (1,000,000). Every tool is read-only; odds are information only.

## Skills and free data

- [83 Claude skills](https://github.com/sports-data-hq/sportsdatahq-skills) for previews, props research, fantasy and DFS, ratings and models, with [example answers](https://github.com/sports-data-hq/sportsdatahq-skills/tree/main/docs/examples).
- A free season of data per sport, as CSV: [sportsdatahq.com/data](https://sportsdatahq.com/data).

Docs: [sportsdatahq.com/docs](https://sportsdatahq.com/docs). Not affiliated with any league, team or sportsbook.
