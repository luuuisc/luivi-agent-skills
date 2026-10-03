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
12. Write this repository's commit messages and PR titles/descriptions in English. Customer-facing content must follow the consuming project's explicit client/audience language policy; do not infer it from the maintainer's language.

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

## Skill catalog and validation

The core V0 workflow is:

1. repo-context
2. spec-driven-development
3. implementation-plan
4. test-strategy
5. code-review
6. pre-merge

The additional catalog is drafted alongside the core workflow so it can be installed and tried incrementally: architecture-decision, branch-start, commit-craft, change-documentation, changelog-maintenance, pr-readiness, and data-change-safety.

Drafting the catalog does not make a skill usable. Validate one skill at a time against a real or realistic task, record evidence and failures, and mark it usable only after its own acceptance criteria are met. Preserve the core workflow's handoff order when a task uses multiple skills. Test optional skills when an appropriate real task arises; do not claim untested cross-agent behavior.

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

The current validation focus is:

skills/spec-driven-development/SKILL.md

It converts a feature request into a concise, reviewable specification before implementation planning. It should hand the specification to `implementation-plan` without repeating repository discovery.

`repo-context` and `implementation-plan` are usable for initial work based on maintainer-reported real-world trials. Preserve each evidence limitation in `docs/validation/`; do not present either as independently evaluated. Other catalog entries remain drafts until validated.
