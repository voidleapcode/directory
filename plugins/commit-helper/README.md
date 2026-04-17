# commit-helper

Voidleap-native plugin that ships a single `commit` skill. The skill reads
`git diff --staged` and emits a Conventional Commit message.

## Install

```
voidleap plugin install voidleap-directory:commit-helper
```

Or pick it from the Directory UI.

## Files

- `.voidleap-plugin/plugin.json` — manifest (Voidleap native format).
- `skills/commit/SKILL.md` — the skill. Declares `bash` in `allowed-tools`,
  so the Directory install dialog flags it as "risky" (expected).

Once installed, the skill is namespaced as `commit-helper:commit`.
