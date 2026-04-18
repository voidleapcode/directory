---
description: Draft a Keep-a-Changelog entry from a short description of a change.
command: changelog-entry
---

# Changelog Entry

Given a one-line description of what changed, produce a properly-formatted
`CHANGELOG.md` entry.

## Steps

1. Classify the change as one of:
   - `Added` — new user-visible feature
   - `Changed` — behaviour of an existing feature changed
   - `Deprecated` — feature marked for removal
   - `Removed` — feature removed
   - `Fixed` — bug fix
   - `Security` — security-relevant change
2. Rewrite the description as a short imperative bullet (no trailing period).
3. If the user already has a `## [Unreleased]` heading in `CHANGELOG.md`,
   append under the appropriate subheading (creating it if absent).
   Otherwise emit a standalone block they can paste in:

   ```md
   ## [Unreleased]

   ### <Category>

   - <bullet>
   ```

## Style

- Prefer "Fix crash when …" over "Fixed a bug where …".
- Don't mention implementation details (file names, function names) — the
  changelog is a user-facing document.
- If the change has a linked issue / PR, suffix with ` (#123)`.
- Wrap lines at roughly 80 columns so the entry reads cleanly on GitHub.
