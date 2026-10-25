---
name: create-workflow
description: Create or revise one team workflow with ordered worker phases.
argument-hint: Team directory, process, and the order in which workers act.
---

Create or revise exactly one workflow in
`<team>/.apm/prompts/<workflow-id>.prompt.md`.

Use the team directory the user names. If they do not name one and the
repository has a single team, use that team.

Use a lowercase kebab-case id from the file name. The id must not match
another prompt in that team. A workflow describes what the team does and in
which order. Reference only existing worker ids. Keep persona content in
workers and procedures in skills.

Repeat the same phase order in the body. Some harnesses drop frontmatter keys
other than the prompt description, and the body is what they execute.

Use this template, replacing the worker ids with workers that already exist:

```markdown
---
description: One-sentence description of this workflow.
phases:
  - id: phase-id
    workers: [worker-id]
---

# Workflow Name

## Order

1. `worker-id` — what this phase decides or produces, and which worker acts next.

## What not to do

- Do not restate a worker's persona or a skill's procedure.
```

Run `apm compile --validate` from the team directory and report the workflow
id, phase order, and result.
