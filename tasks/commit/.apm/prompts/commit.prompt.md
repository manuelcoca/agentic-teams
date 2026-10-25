---
description: Commit one coherent change with a Conventional Commit subject.
---

Commit only the requested work. If the intended scope is unclear, ask before
staging.

1. Inspect `git status`, `git diff`, and `git diff --cached`. Assume staged work
   may be unrelated. Stage only relevant paths or hunks (use explicit paths or
   `git add -p`); preserve unrelated working and staged changes. If you cannot
   exclude unrelated staged work safely, stop and ask.
2. Make each commit independently understandable, reviewable, and reversible.
   Use the "AND" test: split a subject that needs "and" unless the changes are
   inseparable for a coherent, buildable result. Keep implementation and its
   focused tests together; separate independent tests, docs, config, or cleanup.
3. Run the narrowest relevant validation. Do not commit a known failure without
   documenting the reason.
4. Before each commit, review `git diff --cached` and confirm exactly one
   logical change. Use an imperative Conventional Commit subject (for example,
   `feat: implement employee filtering`): `type(scope): summary` or
   `type: summary`, at most 72 characters, no period. Choose `feat`, `fix`,
   `refactor`, `test`, `docs`, `build`, `ci`, `perf`, or `chore` as appropriate.

Report each commit hash and the validation performed.
