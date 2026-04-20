# can-claude-plugins

Personal Claude Code plugin marketplace.

## Plugins

| Plugin | Description | Version |
|--------|-------------|---------|
| [plan-harness](./plan-harness/) | Structured project planning with agent teams. Generates interconnected design docs, test plans, state machines, test cases, and implementation plans as interactive HTML. 11 skills, 6 MCP tools, 6 agent roles. | 1.0.0 |
| [claude-config-manager](https://github.com/wangcansunking/claude-config-manager) | Dashboard & CLI for managing Claude Code configurations — profiles, export/import, MCP store, plugin marketplace, sessions viewer. 9 MCP tools, web dashboard, real-time sync. | 1.0.0-draft |

## Installation

### 1. Add this marketplace

```bash
claude plugins marketplace add https://github.com/wangcansunking/can-claude-plugins
```

### 2. Install a plugin

```bash
# Local plugin (bundled in this repo)
claude plugins install plan-harness@can-claude-plugins

# External plugin (separate repo)
claude plugins install claude-config-manager@can-claude-plugins
```

### 3. Restart Claude Code

The plugin's skills (`/plan-context`, `/plan-init`, `/plan-design`, etc.) and MCP tools will be available.

## Other Commands

```bash
# List installed plugins
claude plugins list

# Update a plugin to latest
claude plugins update plan-harness@can-claude-plugins

# Uninstall a plugin
claude plugins uninstall plan-harness@can-claude-plugins

# List configured marketplaces
claude plugins marketplace list

# Remove this marketplace
claude plugins marketplace remove can-claude-plugins
```

## Adding New Plugins

1. Create a directory at the repo root: `my-new-plugin/`
2. Add `.claude-plugin/plugin.json` with metadata
3. Add skills in `skills/`, MCP server in `local-proxy/`, etc.
4. Register the plugin in the root `.claude-plugin/marketplace.json` under `plugins[]`
5. Commit, push, then run `claude plugins marketplace update can-claude-plugins`
