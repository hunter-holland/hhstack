# hhstack

My collection of skills I use with coding agents.

This repo keeps reusable workflows in one place so I can bring them into different
projects, refine them as I work, and track changes over time. These skills reflect
how I work; adapt them to your own projects and preferences.

## Skills

| Skill | What it does |
| --- | --- |
| [decision-review](skills/decision-review/SKILL.md) | Reviews project decisions, assumptions, and approval history. Produces an evidence-backed decision register and prioritizes choices that need attention. |

## Using a skill

Each skill lives in its own folder under `skills/`. Its `SKILL.md` describes when
to use it, what evidence to inspect, and what the result should look like.
Optional files provide agent metadata or supporting resources.

Install or copy the skill folder into the skills location supported by your
coding agent. Follow that agent's instructions for discovery and invocation.
For agents that support `$skill-name` invocation, an example request is:

```text
Use $decision-review to audit this project's decisions and identify choices
that need my attention.
```

You can also point an agent directly at a skill's `SKILL.md` and ask it to follow
the workflow.

Skills guide the work; they do not grant access or authorize changes. For
example, `decision-review` inspects existing evidence and reports findings;
implementing its recommendations is a separate task.

## Repository layout

```text
skills/
└── decision-review/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

## Maintaining the collection

Keep each skill focused on a reusable task, with a clear description and concise
instructions. Add supporting resources when they make the workflow more useful.
Keep project-specific assumptions and private information out of shared skills,
and update this README when adding or renaming a skill.
