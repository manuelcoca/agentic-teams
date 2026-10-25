---
name: team-artifact-authoring
description: Keep team workers, skills, tasks, and workflows in their proper domain boundaries.
applyTo: "**/.apm/**"
---

# Team artifacts

Each artifact answers one question:

- Worker: "who I am and what I believe". A persona that performs tasks with
  assigned skills. Source file: `.apm/agents/<worker-id>.agent.md`.
- Skill: "how I should do something". A repeatable capability any worker can
  use. Source file: `.apm/skills/<skill-id>/SKILL.md`.
- Task: "what needs to be done". One actionable objective with no worker
  identity and no phase list. Source file: `.apm/prompts/<task-id>.prompt.md`.
- Workflow: "what the team does and in which order". Ordered phases that name
  existing workers. Source file: `.apm/prompts/<workflow-id>.prompt.md`.

A prompt with `phases` is a workflow. A prompt without `phases` is a task.
Task and workflow file names must not collide.

The `skills` list in a worker's frontmatter and the `Assigned skills:` line in
its body are the same assignment. Keep them identical.

Workflow phase order in frontmatter and in the body must name the same workers
in the same order. Persona content stays in the worker. Procedures stay in
skills.
