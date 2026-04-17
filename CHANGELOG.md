# Changelog

## 0.1.0 (initial)

- Seed the Voidleap Directory monorepo.
- Add `commit-helper` plugin (voidleap native format): single `commit` skill
  that generates Conventional Commit messages from staged diffs.
- Add `repo-hygiene` plugin (Claude Code format): `hygiene` skill plus a
  `PreToolUse`/`Bash` hook that blocks secret-adjacent shell input.
- Add `codex-mcp-demo` plugin (Codex format): flat-file `reviewer` agent and
  one HTTP MCP server pointing at `https://httpbin.org/anything/mcp`.
