# Voidleap Directory

Curated plugins maintained by the Voidleap team. This repository is the
source of the `voidleap-directory` marketplace that ships with Voidleap.

## Layout

- `.voidleap-plugin/marketplace.json` — the catalog. Every plugin listed
  here is fetchable from the Directory UI and CLI.
- `plugins/<name>/` — one plugin per directory. Each plugin carries its own
  manifest in whichever format fits the plugin's archetype (Voidleap
  native, Claude Code, or Codex).

## Current plugins

| Name | Format | What it does |
| --- | --- | --- |
| `commit-helper` | Voidleap native | Generates Conventional Commit messages from staged diffs. |
| `repo-hygiene` | Claude Code | Blocks shell commands that touch `.env` files or private keys. |
| `codex-mcp-demo` | Codex | Bundles a concise code-reviewer agent and an HTTP MCP server. |

## Installing

Via CLI:

```
voidleap plugin install voidleap-directory:commit-helper
voidleap plugin install voidleap-directory:repo-hygiene --scope workspace
voidleap plugin install voidleap-directory:codex-mcp-demo --scope project
```

Via UI: open the Directory pane, pick a plugin, confirm the install dialog.

## Contributing

1. Fork and branch.
2. Add a new directory under `plugins/<name>/` with one of
   `.voidleap-plugin/plugin.json`, `.claude-plugin/plugin.json`, or
   `.codex-plugin/plugin.json`.
3. Append the entry to `.voidleap-plugin/marketplace.json`.
4. Bump this repo's `CHANGELOG.md`.
5. Open a PR.

## Repo shape

This is currently a monorepo — plugins live as subdirectories and the
catalog references them by path. Individual plugins can be migrated to
standalone repos later without breaking installs; the catalog entry just
switches from a subdirectory reference to a full repo reference.
