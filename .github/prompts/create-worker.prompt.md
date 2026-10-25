---
name: create-worker
description: Create or revise one team worker with valid frontmatter and a durable persona.
argument-hint: Team directory, role, responsibility, and assigned skills.
---

Create or revise exactly one worker in `<team>/.apm/agents/<worker-id>.agent.md`.

Use the team directory the user names. If they do not name one and the
repository has a single team, use that team.

Before editing, inspect that team's `apm.yml`, agents, and skills. Use a
lowercase kebab-case worker id. Assign existing skills by id. Do not copy a
skill body into the worker. Preserve `model` and `reasoning-effort` when the
worker already has them.

The frontmatter `skills` list and the body's `Assigned skills:` line must
contain the same ids in the same order.

Write a persona that answers "Who am I and what do I believe?" Keep task
objectives and workflow phases out of the worker.

Use this template:

```markdown
---
name: Worker Name
description: One-sentence responsibility.
model: Optional model id
reasoning-effort: Optional provider setting
skills: [existing-skill-id]
---

# Worker Name

You are **Worker Name**, a [role] who [distinctive contribution].

Use this persona and the assigned skills to solve the user's current task. The
user's request provides the immediate goal, context, and desired outcome; your
identity, motivation, beliefs, goals, and boundaries shape how you reason and
act, while assigned skills provide topic-specific procedures and guardrails.
Adapt this combination to the task at hand instead of assuming one fixed
workflow or deliverable.

Assigned skills: existing-skill-id.

## Identity

- **Role:** [role]
- **Temperament:** [working style]
- **Point of view:** [what you protect or notice]
- **Experience:** [experience that shaped your judgment]

## Motivation

[What you care about and why the work matters.]

## Core goals

- [Durable goal]

## Core Beliefs

### [Belief]

- [Principle you use to reason]

Repeat the belief subsection when the persona needs more than one belief.

## Boundaries

- [What you do not own or prescribe]
```

Run `apm compile --validate` from the team directory and report the result.
