# upstox-plugin-marketplace

## Claude Code

Everything here runs inside [Claude Code](https://code.claude.com) — the `/plugin` commands are built-in Claude Code slash commands, and once installed you interact with the skill in plain English.

1. **Open Claude Code** in your terminal (or the desktop/IDE app).
2. **Add the marketplace and install a plugin** (one-time setup):

   ```
   /plugin marketplace add upstox/upstox-plugin-marketplace
   /plugin install upstox-skill@upstox-plugins-official
   /plugin install upstox-mcp@upstox-plugins-official
   ```

> **Add** uses the repository name (`upstox-plugin-marketplace`); **install** uses
> the marketplace name (`@upstox-plugins-official`).

You can also add this marketplace in the **Claude Desktop / web app**: open
**Settings → Plugins** (or **Customize → Plugins**), under **Personal plugins**
click **+ → Add marketplace**, enter `upstox/upstox-plugin-marketplace`, click
**Sync**, then install the plugin you want.


## Featured: [`upstox-skill`](https://github.com/upstox/upstox-skills)

Trade and analyze Indian markets in plain English. The `upstox-skill` plugin connects Claude Code directly to your [Upstox](https://upstox.com) account through the official [`upstox-python-sdk`](https://github.com/upstox/upstox-python), turning natural-language requests into live actions on **NSE, BSE, and MCX** — across equities, F&O, and commodities.

Just ask:

> "What's the LTP of RELIANCE and INFY right now?"
>
> "Show me my open positions and today's P&L."
>
> "Buy 10 shares of TCS at market, but check the margin first."
>
> "Pull the NIFTY option chain for this week's expiry with greeks."

### What it can do

- **Place & manage orders** — place, amend, or cancel orders; resolve the right tradable instrument before anything goes live, and run every order through safety checks first.
- **Inspect your portfolio** — holdings, open positions, available funds, and margin requirements at a glance.
- **Pull live & historical data** — last-traded price, OHLC, full quotes, historical candles, and option chains with greeks.
- **Track performance** — calculate realised and unrealised P&L across your book.
- **Stream in real time** — open a websocket feed for live market ticks and portfolio updates.

### Why it's safe

The skill resolves instruments deterministically and routes every order through pre-trade safety checks — margin, instrument validity, and order parameters — before it reaches the exchange. Nothing is submitted blind.

### Requirements

- An [Upstox](https://upstox.com) account with [API access](https://upstox.com/developer/) enabled
- Upstox API credentials (access token)

See the [`upstox-skills`](https://github.com/upstox/upstox-skills) repository for setup and authentication details.

## Also available: `upstox-mcp`

The `upstox-mcp` plugin connects Claude to the hosted [Upstox MCP server](https://upstox.com/developer/api-documentation/mcp-integration/) (`https://mcp.upstox.com/mcp`) for **read-only, conversational access** to your account — holdings, positions, orders, funds & margin, and profile. Unlike the skill, it needs no Node.js or local setup; Claude connects over HTTP and runs the Upstox OAuth flow in your browser on first use.

```
/plugin install upstox-mcp@upstox-plugins-official
```

> On first use Claude opens your browser for the Upstox OAuth consent. For security, Upstox requires re-authorization once per day.

Use `upstox-mcp` when you want to **analyze and ask questions** about your account; use `upstox-skill` when you want an agent to **build and run trading workflows**.

## Available plugins

| Plugin | Description | Source |
| --- | --- | --- |
| `upstox-skill` | Agent skill for interacting with NSE/BSE equities, F&O, and MCX commodities via the Upstox Developer API. | [upstox/upstox-skills](https://github.com/upstox/upstox-skills) |
| `upstox-mcp` | Remote MCP server for read-only, conversational access to your Upstox account (holdings, positions, orders, funds, profile). | [Upstox MCP docs](https://upstox.com/developer/api-documentation/mcp-integration/) |

