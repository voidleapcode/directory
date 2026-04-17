# Voidleap Directory

Curated plugins maintained by the Voidleap team. This repository is the
source of the `voidleap-directory` marketplace that ships with Voidleap.

## Layout

- `.voidleap-plugin/marketplace.json` — the catalog. Every plugin and
  standalone item listed here is fetchable from the Directory UI and CLI.
- `plugins/<name>/` — one plugin per directory. Each plugin carries its own
  manifest in whichever format fits the plugin's archetype (Voidleap
  native, Claude Code, or Codex).
- `items/skills/<name>/` and `items/agents/<name>/` — standalone skills and
  agents. These have no manifest; the directory's `SKILL.md` / `AGENT.md`
  is the whole thing. They install into `.agents/skills/<name>/` or
  `.agents/agents/<name>/` without any namespace prefix.

## Current plugins

| Name | Format | What it does |
| --- | --- | --- |
| `commit-helper` | Voidleap native | Generates Conventional Commit messages from staged diffs. |
| `repo-hygiene` | Claude Code | Blocks shell commands that touch `.env` files or private keys. |
| `codex-mcp-demo` | Codex | Bundles a concise code-reviewer agent and an HTTP MCP server. |

## Current items

| Name | Kind | What it does |
| --- | --- | --- |
| `changelog-entry` | Skill | Drafts a Keep-a-Changelog entry from a short description. |
| `tldr` | Agent | Condenses long text into a three-line TL;DR. |

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
2. Add either:
   - a **plugin** under `plugins/<name>/` with one of
     `.voidleap-plugin/plugin.json`, `.claude-plugin/plugin.json`, or
     `.codex-plugin/plugin.json`, or
   - a **standalone item** under `items/skills/<name>/` (containing a
     `SKILL.md`) or `items/agents/<name>/` (containing an `AGENT.md`).
3. Append the entry to `.voidleap-plugin/marketplace.json` (in `plugins`
   or `items` as appropriate).
4. Bump this repo's `CHANGELOG.md`.
5. Open a PR.

## Repo shape

This is currently a monorepo — plugins live as subdirectories and the
catalog references them by path. Individual plugins can be migrated to
standalone repos later without breaking installs; the catalog entry just
switches from a subdirectory reference to a full repo reference.
