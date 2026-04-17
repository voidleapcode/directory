---
description: Generate a Conventional Commit message from staged changes.
command: commit
allowed-tools:
  - bash
  - read
---

# Commit Helper

1. Run `git diff --staged` and summarise the change.
2. Pick the smallest accurate Conventional Commit type (feat, fix, refactor,
   docs, chore, test).
3. Output `<type>(<scope>): <subject>` followed by an optional body.
