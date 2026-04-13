# canwa-claude-plugins

Personal Claude Code plugin marketplace.

## Plugins

| Plugin | Description | Version |
|--------|-------------|---------|
| [plan-harness](./plan-harness/) | Structured project planning with agent teams. Generates interconnected design docs, test plans, state machines, test cases, and implementation plans as interactive HTML. 11 skills, 6 MCP tools, 6 agent roles. | 1.0.0 |

## Installation

### Register this marketplace

Add to `~/.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "canwa-claude-plugins": {
      "source": {
        "source": "git",
        "url": "file:///C:/repos/canwa-claude-plugins"
      }
    }
  }
}
```

### Enable a plugin

```json
{
  "enabledPlugins": {
    "plan-harness@canwa-claude-plugins": true
  }
}
```

Then restart Claude Code. The plugin's skills (`/plan-context`, `/plan-init`, `/plan-design`, etc.) and MCP tools will be available.

## Adding New Plugins

1. Create a directory at the repo root: `my-new-plugin/`
2. Add `.claude-plugin/plugin.json` with metadata
3. Add skills in `skills/`, MCP server in `local-proxy/`, etc.
4. Commit and the plugin is available in Claude Code
