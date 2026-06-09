# upstox-plugin-marketplace

The **`upstox-plugins-official`** [Claude Code](https://code.claude.com) plugin marketplace — a central catalog of Upstox plugins for Claude Code.

## Installation

Add the marketplace, then install a plugin from it:

```
/plugin marketplace add upstox/upstox-plugin-marketplace
/plugin install upstox-skill@upstox-plugins-official
```

## Available plugins

| Plugin | Description | Source |
| --- | --- | --- |
| `upstox-skill` | Agent skill for interacting with NSE/BSE equities, F&O, and MCX commodities via the Upstox Developer API. | [upstox/upstox-skills](https://github.com/upstox/upstox-skills) |

## Contributing

Plugins are registered in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json). To add a plugin, append an entry to the `plugins` array pointing at its source repository.
