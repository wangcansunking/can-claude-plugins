# canwa-claude-plugins

Personal Claude Code plugin marketplace.

## Plugins

| Plugin | Description | Version |
|--------|-------------|---------|
| [plan-harness](./plan-harness/) | Structured project planning with agent teams. Generates interconnected design docs, test plans, state machines, test cases, and implementation plans as interactive HTML. 11 skills, 6 MCP tools, 6 agent roles. | 1.0.0 |

## Installation

### 1. Add this marketplace

```bash
claude plugins marketplace add https://github.com/wangcansunking/sunky-claude-code-marketplace
```

### 2. Install a plugin

```bash
claude plugins install plan-harness@canwa-claude-plugins
```

### 3. Restart Claude Code

The plugin's skills (`/plan-context`, `/plan-init`, `/plan-design`, etc.) and MCP tools will be available.

## Other Commands

```bash
# List installed plugins
claude plugins list

# Update a plugin to latest
claude plugins update plan-harness@canwa-claude-plugins

# Uninstall a plugin
claude plugins uninstall plan-harness@canwa-claude-plugins

# List configured marketplaces
claude plugins marketplace list

# Remove this marketplace
claude plugins marketplace remove canwa-claude-plugins
```

## Adding New Plugins

1. Create a directory at the repo root: `my-new-plugin/`
2. Add `.claude-plugin/plugin.json` with metadata
3. Add skills in `skills/`, MCP server in `local-proxy/`, etc.
4. Register the plugin in the root `.claude-plugin/marketplace.json` under `plugins[]`
5. Commit, push, then run `claude plugins marketplace update canwa-claude-plugins`
