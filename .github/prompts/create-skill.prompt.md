---
name: create-skill
description: Create or revise one reusable team skill with valid frontmatter and clear procedures.
argument-hint: Team directory, capability, method, and guardrails.
---

Create or revise exactly one skill at
`<team>/.apm/skills/<skill-id>/SKILL.md`.

Use the team directory the user names. If they do not name one and the
repository has a single team, use that team.

Use a lowercase kebab-case id matching the directory name. Keep the skill
independent of worker personality, task output, and workflow order.

Every new skill must use this frontmatter:

```yaml
---
name: skill-id
description: One-sentence reusable capability. Use when [trigger].
user-invocable: true
disable-model-invocation: false
---
```

Do not add `license`, `compatibility`, or `metadata` to a new skill. Leave
those fields in place when they already belong to an upstream skill.

There is no fixed body template. Explain how to apply the capability and the
guardrails that matter. Add `references/` or `assets/` beside `SKILL.md` when
the procedure needs them.

Inspect existing workers before assigning the skill. Add the id to a worker's
`skills` list and `Assigned skills:` line only when that worker should use it.
Do not add a worker to a workflow unless the user asks.

Run `apm compile --validate` from the team directory and report the result.
