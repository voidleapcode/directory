# commit-helper

Voidleap-native plugin that ships a single `commit` skill. The skill reads
`git diff --staged` and emits a Conventional Commit message.

## Install

```
voidleap plugin install voidleap-directory:commit-helper
```

Or pick it from the Directory UI.

## Files

- `.voidleap-plugin/plugin.json` — manifest (voidleap native format).
- `skills/commit/SKILL.md` — the skill. Declares `bash` in `allowed-tools`,
  so the Directory install dialog flags it as "risky".

Namespaced as `commit-helper:commit` once installed (see
`src/docs/22-plugins.md`).
