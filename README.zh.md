[English](README.md) · **简体中文**

---

# can-claude-plugins

Claude Code 个人插件市场。

## 插件

| 插件 | 简介 | 版本 |
|------|------|------|
| [plan-harness](https://github.com/wangcansunking/plan-harness) | 结构化项目规划工具，搭配 agent 团队使用。统一的 `/plan-gen` 分派器可生成全部文档类型（design / state-machine / test-plan / test-cases / implementation / test-report / analysis），支持级联同步、搭配 Playwright MCP 的交互式 test-report 修复循环、带 W3C 风格锚点的内置评论 UI。10 个 skill、12 个 MCP 工具、6 个 agent 角色。 | 1.2.0 |
| [claude-config-manager](https://github.com/wangcansunking/claude-config-manager) | 管理 Claude Code 配置的 Dashboard + CLI — 配置档案、导出/导入、MCP 市场、插件市场、会话、指标。CLI 优先（`claude-config`）+ 5 个 slash command + 2 个 MCP 工具的极简面。 | 1.1.0 |

## 安装

### 1. 添加本市场

```bash
claude plugins marketplace add https://github.com/wangcansunking/can-claude-plugins
```

### 2. 安装插件

```bash
# 市场本仓自带的插件
claude plugins install plan-harness@can-claude-plugins

# 独立仓库的插件
claude plugins install claude-config-manager@can-claude-plugins
```

### 3. 重启 Claude Code

重启后，插件的 skill（例如 `/plan-context`、`/plan-init`、`/plan-gen`、`/plan-sync` 等）和 MCP 工具就可用了。

## 其他命令

```bash
# 列出已安装插件
claude plugins list

# 更新某个插件到最新
claude plugins update plan-harness@can-claude-plugins

# 卸载插件
claude plugins uninstall plan-harness@can-claude-plugins

# 查看已配置的市场
claude plugins marketplace list

# 移除本市场
claude plugins marketplace remove can-claude-plugins
```

## 新增插件

1. 在仓库根目录新建一个文件夹：`my-new-plugin/`
2. 加 `.claude-plugin/plugin.json`，写元数据
3. 在 `skills/` 放 skill，`local-proxy/` 放 MCP server，依此类推
4. 把插件注册到仓库根的 `.claude-plugin/marketplace.json` 的 `plugins[]` 下
5. 提交、推送后执行 `claude plugins marketplace update can-claude-plugins`
