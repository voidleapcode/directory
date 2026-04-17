# repo-hygiene

Claude Code-format plugin that registers a `PreToolUse` hook matching the
`Bash` tool. The hook blocks (exit 2) any Bash input that references a
`.env` file or a private-key extension (`.p12`, `.pem`, `.pfx`, `.key`).

## Install

```
voidleap plugin install voidleap-directory:repo-hygiene --scope workspace
```

## Files

- `.claude-plugin/plugin.json` — CC-format manifest. Voidleap's translator
  detects the `.claude-plugin/` directory and applies the CC-format pipeline
  (`src/core/plugins/translate/cc.ts`).
- `skills/hygiene/SKILL.md` — reference skill for users asking about git
  hygiene.
- `hooks/hooks.json` — CC-nested shape. Voidleap's hook translator
  (`src/core/plugins/translate/hooks.ts`) flattens this into the scope's
  hooks JSON.
