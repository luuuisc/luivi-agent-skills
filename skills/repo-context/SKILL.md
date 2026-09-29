---
name: repo-context
description: Map an unfamiliar repository before planning or editing code, covering architecture, stack, commands, conventions, tests, relevant files, and risks. Use for repository discovery; do not use as a substitute for implementation planning or code review.
---

# Repository Context

## Trigger

Use when a coding task requires understanding a repository before implementation, planning, or review, especially when the repository is unfamiliar or its conventions are unclear.

## Purpose

Produce a concise, evidence-based `Repository Context Map` that gives the next engineering workflow enough context to make safe decisions.

## Inputs

- Repository root and the user's task, if provided.
- Repository instructions, including applicable `AGENTS.md` files.
- Tracked files, configuration, manifests, source layout, documentation, tests, and available version-control metadata.

## Workflow

1. Establish the repository root and read applicable instructions before interpreting or changing anything.
2. Inventory the repository with fast, targeted file discovery. Prioritize manifests, lockfiles, build and CI configuration, entry points, documentation, source directories, and test directories.
3. Identify the stack and runtime from configuration and dependency files. Record versions only when they are stated by repository evidence.
4. Trace the high-level architecture: application or package boundaries, key entry points, major layers, generated code, external integrations, and important data or control flows.
5. Discover documented commands for install, development, build, lint, type-checking, testing, and formatting. Distinguish documented commands from commands inferred from tooling.
6. Inspect representative source and test files to identify naming, structure, error handling, dependency, mocking, and test conventions. Do not read every file by default.
7. For the user's task, identify the most relevant files, neighboring tests, likely change boundaries, and dependencies between affected components.
8. Record risks, unknowns, and assumptions separately. Cite paths (and line numbers when useful) for material findings.
9. Run only lightweight, read-only validation commands when they clarify the map. Do not install dependencies, edit files, reset state, or run expensive suites unless the user explicitly requests that work.

## Validation rules

- Every material claim is grounded in a file, command result, or clearly labeled inference.
- The map covers architecture, stack, commands, conventions, tests, relevant files, and risks.
- Commands include their source or are labeled as inferred; never present guesses as repository facts.
- The task scope is narrowed to concrete files and components where repository evidence permits.
- Missing documentation, unavailable dependencies, dirty working-tree state, and unresolved architecture are reported rather than hidden.

## Failure conditions

Stop and report the limitation when the repository root cannot be established, applicable instructions cannot be read, or the task cannot be related to any repository component after targeted discovery. Continue with a partial map when only optional evidence is unavailable, and clearly identify the gap.

## Expected output

Return a `Repository Context Map` with these sections:

- **Scope** — task understood and repository root.
- **Architecture** — boundaries, entry points, and important flows.
- **Stack** — languages, frameworks, runtimes, and significant dependencies.
- **Commands** — install, run, build, lint, type-check, test, and format commands with evidence or inference labels.
- **Conventions** — relevant source and test patterns.
- **Relevant files** — files to inspect or likely change, with why each matters.
- **Risks and unknowns** — technical, testing, integration, generated-file, or environment risks.
- **Confidence** — confirmed facts, inferences, and unanswered questions.

Keep the output proportional to the task. Prefer precise paths and short explanations over a comprehensive repository dump.

## Boundaries

- This skill observes and maps; it does not implement, refactor, plan the solution, review code, or modify repository state.
- Do not infer project-specific rules from generic conventions when repository evidence is absent.
- Do not expand the investigation into unrelated packages or historical commits unless the task requires it.
- Do not add scripts, references, evals, or directory structure solely to support this first pass; add them only after a demonstrated reliability need.
