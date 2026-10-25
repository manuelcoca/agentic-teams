# Agentic teams

Each top-level directory that contains an `apm.yml` is one team, and one
[Agent Package Manager](https://microsoft.github.io/apm/) module. Install the
team you need into a project. Add another team by adding another directory.

A team has four roles:

- **Workers** answer "who I am and what I believe". A worker is a persona with
  a durable identity, motivation, goals, beliefs, judgment, and boundaries.
  APM installs it as an agent.
- **Skills** answer "how I should do something". They are reusable,
  worker-independent procedures and guardrails. A worker lists the skills it
  uses; the skill does not belong to one worker.
- **Tasks** answer "what needs to be done". A task is one actionable,
  worker-neutral objective. APM installs it as a prompt.
- **Workflows** answer "what the team does and in which order". A workflow
  names existing workers in phases. APM installs it as a prompt. The phase
  order is in the prompt body, because some harnesses keep only the prompt
  description from frontmatter.

Tasks and workflows share the prompt directory, so their file names must be
unique inside one team.

## Install a team

From the project that should receive the team:

```bash
apm install manuelcoca/agentic-teams/software-development
```

APM deploys that module's agents, skills, and prompts into the harnesses it
detects. Append `#<tag-or-commit>` when you need a fixed revision.

## Package layout

```text
<team>/
  apm.yml
  .apm/agents/<worker-id>.agent.md
  .apm/skills/<skill-id>/SKILL.md
  .apm/prompts/<task-id>.prompt.md
  .apm/prompts/<workflow-id>.prompt.md
```

| Role | File | Id |
| --- | --- | --- |
| Worker | `.apm/agents/<worker-id>.agent.md` | file name |
| Skill | `.apm/skills/<skill-id>/SKILL.md` | directory name |
| Task | `.apm/prompts/<task-id>.prompt.md` | file name, no `phases` |
| Workflow | `.apm/prompts/<workflow-id>.prompt.md` | file name, has `phases` |

Worker frontmatter keeps `skills`, `model`, and `reasoning-effort`. The body
repeats the skill ids on an `Assigned skills:` line so the persona still sees
them when a harness ignores that frontmatter key. Skill ids in both places
must match.

## Teams

- `software-development`: architect, Go backend engineer, and frontend
  engineer, plus their skills and shared tasks.

## Authoring

Edit the team source under `<team>/.apm/`. The `.github/` prompts in this
repository create and review those files. They are editor help for this
catalog, not part of an installed team.

From the team directory:

```bash
apm compile --validate
```

Do not commit `apm_modules/` or files APM generates into a consumer project.
The source of a team is `apm.yml` and `.apm/`.
