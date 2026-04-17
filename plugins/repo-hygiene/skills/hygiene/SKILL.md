---
description: Explain common repo-hygiene issues and how to fix them.
---

# Repo Hygiene

Use this skill when a user asks about `.gitignore`, large files, or secrets
in git history. Prefer `git lfs` for binaries >1 MB and `git filter-repo`
(never `filter-branch`) for secret removal.
