# codex-mcp-demo

Codex-format plugin that bundles a single-file `reviewer` agent and one HTTP
MCP server entry. After translation you should see:

- `.agents/agents/@codex-mcp-demo/reviewer/AGENT.md` — folder-wrapped agent
  with `tools: {"allow":["read","grep","glob"]}` frontmatter (the
  translator rewrites CC/Codex array-style `tools` into our schema).
- `.agents/mcp/@codex-mcp-demo/httpbin.md` — HTTP MCP entry pointing at
  `https://httpbin.org/anything/mcp` (a convenient reflector for smoke
  testing; it is not a real MCP server).

Install:

```
voidleap plugin install voidleap-directory:codex-mcp-demo --scope project
```
