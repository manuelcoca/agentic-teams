# Agentic teams

A catalog of [Agent Package Manager](https://microsoft.github.io/apm/) modules
for building an agent team. Every module is installed on its own, so a team is
whichever modules you install together.

## How we think about it

- **Workers** answer "who I am and what I believe". A worker is a persona: a
  durable identity, motivation, goals, beliefs, judgment, and boundaries. It
  can bring skills and tasks that only that worker needs.
- **Skills** answer "how I should do something". They are procedures and
  guardrails. A specialized worker comes with its own specialized skills.
- **Tasks** answer "what needs to be done". A task is one actionable
  objective. It belongs to a worker when only that worker should perform it.
  Otherwise it is its own module, and it can bring the skill it depends on.
- **Workflows** answer "what the team does and in which order". A workflow
  names existing workers in phases. It does not carry their skills or tasks.

## Repository layout

```text
workers/<worker>/   a persona and its worker-specific skills and tasks
tasks/<task>/       a task several workers can perform, plus its skill if needed
```

Each of those directories is one module with its own `apm.yml` and `.apm/`
folder. Workflows will get their own top-level folder.

## Install

From the project that should receive a module:

```bash
apm install manuelcoca/agentic-teams/workers/software-architect --target opencode --legacy-skill-paths
```

Replace the path with any module under `workers/` or `tasks/`.
`--legacy-skill-paths` installs skills under `.opencode/skills/`. Append
`#<tag-or-commit>` for a fixed revision.

## Module layout

```text
<module>/
  apm.yml
  .apm/agents/<worker-id>.agent.md
  .apm/skills/<skill-id>/SKILL.md
  .apm/prompts/<task-id>.prompt.md
```

The files under `.apm/` are the OpenCode documents. APM installs agents to
`.opencode/agents/`, prompts as `.opencode/commands/`, and skills to
`.opencode/skills/`, removing the `.agent` and `.prompt` part of the file name.

## Authoring

Edit a module under `<module>/.apm/`. Validate a worker module from its
directory:

```bash
apm compile --validate
```

`apm compile` only checks agents and instructions, so it reports nothing to
validate for a task module.

Do not commit `apm_modules/` or files APM generates into a consumer project.
