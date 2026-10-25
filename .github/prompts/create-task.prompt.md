---
name: create-task
description: Create or revise one team task with valid frontmatter and clear instructions.
argument-hint: Team directory, goal, actions, and exclusions.
---

Create or revise exactly one task in `<team>/.apm/prompts/<task-id>.prompt.md`.

Use the team directory the user names. If they do not name one and the
repository has a single team, use that team.

Use a lowercase kebab-case id from the file name. The id must not match
another prompt in that team. A task describes what needs to be done: one
actionable objective a worker can perform with its assigned skills. Keep
worker identity in workers, procedures in skills, and multi-worker order in
workflows. Do not add a `phases` key.

Use this template:

```markdown
---
description: One-sentence task description.
---

## What is the goal

Describe the outcome this task should achieve.

## What to do

- [Instruction or step]
- [Instruction or step]

## What not to do

- [Constraint, exclusion, or failure mode to avoid]
```

Write the task as direct instructions to the worker. Use paragraphs and bullet
lists where they make the task clearer. Do not add an `id` frontmatter field.
Do not invoke another prompt from the task body.

Run `apm compile --validate` from the team directory and report the task id
and result.
