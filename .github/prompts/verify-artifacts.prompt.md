---
name: verify-artifacts
description: Verify team artifacts against their domain boundaries and suggest improvements when necessary.
argument-hint: Team directory to review, or leave empty to review every team.
---

Verify team artifacts against the team domain. Suggest an improvement only
when an artifact breaks that boundary.

Review each team the user names. If they name none, review every directory
that contains `apm.yml`.

For each team, read:

- `apm.yml`
- `.apm/agents/`
- `.apm/skills/`
- `.apm/prompts/`

Use the [team artifact authoring instruction](../instructions/team-artifact-authoring.instructions.md)
as the source of truth.

For each artifact:

- Check its boundary, frontmatter, references, and scope.
- A worker's `skills` list and `Assigned skills:` line must match, and every
  id must exist under `.apm/skills/`.
- A prompt with `phases` is a workflow. Its body must list the same workers in
  the same order, and every worker id must exist.
- A prompt without `phases` is a task and must not coordinate multiple workers.
- Prompt file names must be unique inside the team.
- Identify violations, overlap, and inconsistencies.
- Suggest the smallest useful change, with the artifact path and the reason,
  only when something fails.
- Report "No issue" when it passes review.

Do not edit artifacts during verification unless the user asks for the
suggested changes to be applied.
