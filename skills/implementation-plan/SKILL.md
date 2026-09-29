---
name: implementation-plan
description: Turn a non-trivial engineering request and available repository context into a scoped, testable plan before code changes. Use for implementation planning and bounded multi-agent work; do not use for repository discovery alone or to implement the change.
---

# Implementation Plan

## Trigger

Use before implementing a non-trivial feature, refactor, integration, or bug fix when the work benefits from explicit scope, dependencies, verification, or coordination. Skip a formal plan for a trivial change unless the user asks for one.

## Purpose

Produce a concise, evidence-based `Implementation Plan` that an engineer or small set of agents can execute without repeating repository discovery or guessing at completion criteria.

## Inputs

- User request, constraints, and decisions.
- Applicable repository instructions.
- A `Repository Context Map` when available.
- Relevant issue, design, or acceptance material supplied by the user.

## Workflow

1. Restate the requested outcome in concrete terms. Separate explicit constraints and decisions from assumptions.
2. Reuse the current `Repository Context Map` when available. If it is missing or stale on a plan-critical detail, inspect only the relevant files and report any remaining evidence gap; avoid redoing broad discovery.
3. Define scope and non-goals. If an unresolved product choice would materially change the implementation, expose it as an open decision instead of silently choosing.
4. Identify affected files, components, data flows, and dependencies. Tie each proposed change to repository evidence or label it tentative.
5. Order the smallest coherent implementation steps, including necessary migrations, compatibility handling, or rollout sequencing when the task requires them.
6. Define verification using repository-supported commands and tests. Distinguish existing tests from tests that would need to be added; do not claim a command exists without evidence.
7. State concrete acceptance criteria and risks that could change the plan.
8. If the work is genuinely parallelizable, define a small number of agent tasks with separate ownership, exact inputs, expected outputs, and integration dependencies. Keep shared-file conflicts and cross-agent dependencies explicit. Otherwise keep the plan serial.
9. Return the plan in the format below, proportional to task complexity.

## Validation rules

- Scope traces back to the user's request; no unrelated cleanup is introduced.
- Relevant files, dependencies, and commands are grounded in repository evidence or marked tentative.
- Verification steps have observable outcomes and fit the change's risk.
- Risks, assumptions, and unresolved decisions are visible.
- Delegated tasks are independent enough to run concurrently and have clear ownership and handoff artifacts; do not delegate merely to increase agent count.
- The skill does not edit files or perform implementation actions.

## Failure conditions

If the desired outcome or a decision with major architectural consequences is unclear, present a partial plan and identify the blocking question. If repository access or the context artifact is missing, explain what cannot be grounded and avoid fabricating paths, commands, or system behavior.

## Expected output

Return an `Implementation Plan` with:

- **Goal** — requested outcome and non-goals.
- **Context used** — relevant Repository Context Map or files inspected.
- **Plan** — ordered steps with affected files/components and rationale.
- **Verification** — tests/commands to run and expected signals.
- **Risks and open decisions** — items that could change scope or implementation.
- **Agent split** — include only when parallel work is useful; state owner, inputs, deliverable, and dependencies for each task.
- **Acceptance criteria** — observable conditions for completion.

Keep the plan compact. Carry forward only facts needed to execute this task; do not paste the whole repository map or conversation history.

## Boundaries

- This skill plans; it does not edit code, execute tests, install dependencies, commit, or deploy.
- Do not repeat repository discovery already captured in a current context map.
- Do not make product or architecture decisions on the user's behalf when the choice materially changes the result.
- Do not force parallel agents onto work with shared ownership or tight dependencies.
