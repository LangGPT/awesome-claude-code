# Awesome Claude Code [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of Claude Code plugins, MCP servers, editor integrations, and resources

## How to use

Many resources can be installed directly via Claude Code commands:
```bash
# Add a marketplace
/plugin marketplace add ananddtyagi/claude-code-marketplace

# Install a specific plugin
/plugin install <owner>/<repo>
```

## Plugins & Extensions
- [Claude Code Commands Marketplace](https://github.com/ananddtyagi/claude-code-marketplace) - Community marketplace for Claude Code commands and plugins; add with `/plugin marketplace add ananddtyagi/claude-code-marketplace`.
- [Claude Code Plugins (jeremylongshore)](https://github.com/jeremylongshore/claude-code-plugins) - Marketplace-style repo bundling instruction-template plugins and MCP plugin packs, with install docs.
- [Multi-Agent Intelligence Marketplace](https://github.com/jmanhype/claude-code-plugins) - 19 production-grade plugins for trading, swarm intelligence, and GitHub automation built from 68+ specialized agents. Includes quantitative trading systems, DSPy research pipelines, distributed consensus protocols, and multi-agent swarm coordination; add with `/plugin marketplace add jmanhype/claude-code-plugins`.
- [Docker Claude Plugins](https://github.com/docker/claude-plugins) - Integrates Docker Desktop's MCP Toolkit as a Claude Code plugin to expose containerized MCP servers through Claude.

## MCP Servers
- [Atlassian Remote MCP Server](https://developer.atlassian.com/platform/model-context-protocol/) - OAuth-secured remote MCP for Jira/Confluence (Claude setup + cloud endpoints).
- [BGPT MCP](https://github.com/connerlambden/bgpt-mcp) - Hosted MCP server for searching scientific papers with full-text experimental data; SSE + Streamable HTTP endpoints.
- [GitHub MCP Server](https://github.com/modelcontextprotocol/servers/tree/main/src/github) - Official first-party server to read repos, manage issues/PRs, and automate workflows.
- [Google Workspace MCP](https://github.com/aekanun2020/Google-MCP-Servers) - Community server with Sheets/Drive/Gmail/Calendar/Docs/Slides/Tasks coverage with remote OAuth and 1-click Claude install.
- [Notion MCP](https://www.notion.so/help/add-and-manage-connections-with-the-api#mcp) - Official hosted server with OAuth; designed for Claude/Cursor/etc.
- [Supabase MCP Server](https://supabase.com/blog/supabase-mcp) - Official server to connect Claude to Supabase projects; HTTP/SSE transports and OAuth supported.

## Editor Plugins
- [Claude Code for JetBrains](https://plugins.jetbrains.com/plugin/26099-claude-code) - Official plugin for IntelliJ family (interactive diffs, selection context) (Beta).
- [Claude Code for VS Code](https://marketplace.visualstudio.com/items?itemName=Anthropic.claude-code) - Official marketplace extension; inline diffs, real-time edits.
- [claude-chat.nvim](https://github.com/ribru17/claude-chat.nvim) - Neovim wrapper around the Claude Code CLI (shares file/selection context).
- [claude-code.nvim](https://github.com/greggh/claude-code.nvim) - Community Neovim integration built using Claude Code inside Neovim.
- [claudecode.nvim](https://github.com/coder/claudecode.nvim) - Neovim IDE integration for Claude Code (pure Lua).
- [Claude Code Chat](https://marketplace.visualstudio.com/items?itemName=nishant.claude-code-chat) - Community GUI chat/front-end for Claude Code inside VS Code.

## Documentation & Learning Resources
- [Customize Claude Code with plugins](https://www.anthropic.com/news/customize-claude-code-with-plugins) - Official announcement intro to plugins (commands, agents, MCPs, hooks).
- [Plugin marketplaces](https://docs.claude.com/en/docs/claude-code/plugins#plugin-marketplaces) - Guide on how to create/distribute marketplaces and team-install via `.claude/settings.json`.
- [Connect Claude Code to tools via MCP](https://docs.claude.com/en/docs/claude-code/mcp) - Official MCP integration guide for Claude Code.
- [VS Code integration docs](https://docs.claude.com/en/docs/claude-code/vs-code) - Official docs for the VS Code extension.
- [JetBrains integration docs](https://docs.claude.com/en/docs/claude-code/jetbrains) - Official docs for JetBrains plugin.
