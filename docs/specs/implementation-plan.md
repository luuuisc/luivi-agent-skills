# Skill Spec: implementation-plan

**Status:** Usable for initial work based on maintainer-reported success; incomplete evaluation record

## Problem

Agents often move from a feature request directly into edits. That can widen scope, miss dependencies, duplicate repository discovery, or leave testing and acceptance criteria until the end. When several agents are involved, vague task splits create overlapping edits and large, low-signal handoffs.

## Intended use

Before a non-trivial implementation, turn the user's task and available repository evidence into a focused plan that one engineer or a small set of agents can execute and verify.

## Inputs

- The user's requested outcome, constraints, and known decisions.
- Applicable repository instructions.
- A `Repository Context Map` when available; otherwise enough targeted repository evidence to identify relevant components and clearly state remaining gaps.
- Existing issue, design, or acceptance material when the user provides or references it.

## Output

A concise `Implementation Plan` with:

- goal and non-goals
- assumptions and open decisions
- affected files or components, with evidence
- ordered implementation steps
- validation strategy and relevant commands/tests
- risks and dependencies
- observable acceptance criteria
- optional agent assignments with ownership and handoff artifacts when the work is truly separable

## Boundaries

- Plan only; do not edit code, install dependencies, run migrations, commit, or deploy.
- Do not repeat broad repository discovery when a current `Repository Context Map` already answers the question.
- Do not invent file paths, commands, dependencies, or acceptance criteria; label inference and unknowns.
- Do not split work across agents just to use more agents. Delegate only independent work with clear ownership and integration boundaries.

## Acceptance criteria

- A capable engineer can begin execution from the plan without rediscovering the same repository structure.
- Every proposed file or component change is tied to task scope and repository evidence, or labeled as tentative.
- The plan includes verification and observable completion criteria appropriate to the task.
- Unknowns that could change the plan are surfaced before they become hidden assumptions.
- Any parallel agent tasks are independent, bounded, and have explicit inputs, outputs, and ownership; otherwise the plan stays serial.
- The skill produces no repository edits or other implementation side effects.

## Validation approach

See [`../validation/implementation-plan.md`](../validation/implementation-plan.md) for the current maintainer-reported result and its evidence limitations. Repeat a real non-trivial task in Dulio or the CRM project with a privacy-reviewed request, context map, and resulting plan before claiming independent or repeatable validation.
