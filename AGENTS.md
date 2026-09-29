# AGENTS.md

## Project purpose

This repository contains reusable engineering skills for coding agents.

The goal is not to build a prompt collection.

The goal is to create tested, reusable engineering workflows that improve:

- repository understanding
- implementation planning
- code quality
- test coverage
- review quality
- development velocity

Dulio is the primary real-world proving ground for these skills.

## Core principles

1. Context before code.
2. One skill should solve one clear engineering problem.
3. Prefer explicit workflows over vague prompts.
4. Do not add scripts unless deterministic execution improves reliability.
5. Do not add complexity without a real use case.
6. Skills should be reusable when possible.
7. Project-specific knowledge belongs in project AGENTS.md files or project-local skills.
8. Every skill should eventually be tested on real engineering work.
9. Evals should be added when quality can be measured.
10. Never optimize for quantity of skills. Optimize for usefulness.
11. Optimize context for useful signal: keep discovery metadata small, load detailed workflow guidance only when relevant, and avoid repeating repository facts already captured in project instructions or prior artifacts.

## Repository architecture

skills/
Reusable skill definitions.

docs/
Architecture, standards and design decisions.

evals/
Controlled tests and benchmarks for skills.

scripts/
Deterministic utilities used by skills.

references/
Supporting knowledge used by skills.

examples/
Real or synthetic examples showing expected behavior.

## Skill standard

Every skill must define:

- Trigger
- Purpose
- Inputs
- Workflow
- Validation rules
- Failure conditions
- Expected output
- Boundaries

Design each workflow to consume and produce concise artifacts that can be handed to a later workflow or agent without repeating the full investigation.

A skill may optionally include:

- scripts/
- references/
- assets/
- evals/

Do not add optional directories unless needed.

## Current V0

Build these skills in this order:

1. repo-context
2. implementation-plan
3. test-strategy
4. code-review
5. pre-merge

Do not start the next skill until the previous one is usable.

## Development workflow

For each skill:

1. Write or update a short spec with the repeated problem, intended users, scope, and observable acceptance criteria.
2. Write the smallest useful `SKILL.md` that meets those criteria.
3. Test it against a real or realistic repository task.
4. Record the prompt, context, outcome, and failures; distinguish observed evidence from maintainer-reported results.
5. Improve instructions only in response to evidence or a clarified requirement.
6. Add scripts only when deterministic execution improves reliability.
7. Add an eval when behavior can be measured consistently.
8. Mark the skill usable only when the acceptance criteria are met with recorded evidence.

For cross-agent work, use the portable Agent Skills format for shared workflow content. Document tool-specific discovery paths and metadata separately; do not assume that `AGENTS.md`, `CLAUDE.md`, editor rules, and skills are interchangeable.

## Current focus

The active skill is:

skills/implementation-plan/SKILL.md

It consumes a task and a `Repository Context Map` to produce a small, evidence-based implementation plan before code changes.

The previous skill, `repo-context`, is usable for initial work based on a successful maintainer-reported real-world trial. Preserve its evidence limitation in `docs/validation/repo-context.md`; do not present it as independently evaluated.
