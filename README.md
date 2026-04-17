# Voidleap Directory

Curated plugins maintained by the Voidleap team. This repository backs the
hardcoded `voidleap-directory` marketplace in Voidleap — see
`VOIDLEAP_CATALOG` in `src/core/plugins/marketplace.ts`.

## Layout

- `.voidleap-plugin/marketplace.json` — catalog. Validated against
  `MarketplaceIndexSchema` (`src/core/plugins/schema.ts`). Each entry uses
  the `git-subdir` source and points at a subdirectory of this repo.
- `plugins/<name>/` — one plugin per directory. Each plugin carries its own
  manifest in the format appropriate for its archetype (voidleap native,
  Claude Code, or Codex); Voidleap's translator detects the format from
  the manifest directory (`.voidleap-plugin/`, `.claude-plugin/`, or
  `.codex-plugin/`).

## Current plugins

| Name | Format | Exercises |
| --- | --- | --- |
| `commit-helper` | voidleap native | skill loader namespace `@<plugin>/`, "risky tool" install flag |
| `repo-hygiene` | Claude Code | CC manifest detection, CC → Voidleap hook translation |
| `codex-mcp-demo` | Codex | Codex detection, CC-style agent frontmatter rewrite, `.mcp.json` HTTP translation |

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

Authoring reference: `src/docs/22-plugins.md` in the Voidleap repo.

## Layout note

This repo is currently a monorepo — plugins live as subdirectories and the
catalog references them via `git-subdir`. Voidleap's cache layer
(`src/core/plugins/cache.ts`) already supports extracting per-plugin repos
later without any client change; we'd just flip each marketplace entry's
`source` from `git-subdir` to `github` and publish a standalone repo.
