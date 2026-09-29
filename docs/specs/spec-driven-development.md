# Skill Spec: spec-driven-development

**Status:** Draft, V0

## Problem

Feature requests often mix desired user outcomes with assumptions and solution ideas. If implementation begins before behavior and acceptance are clear, agents can build the wrong thing or pass an underspecified task to another agent.

## Intended use

For a new or materially changed feature, turn the request and relevant project evidence into a concise, reviewable specification before implementation planning. The spec should be useful to a later `implementation-plan` workflow without repeating discovery.

## Inputs

- User request, constraints, decisions, and any supplied product/design references.
- Applicable project instructions.
- A current `Repository Context Map` when project behavior or constraints matter; otherwise targeted evidence only as needed.

## Output

A concise `Feature Specification` containing the user/problem outcome, scope and non-goals, observable requirements and acceptance criteria, important scenarios, assumptions/open questions, and evidence references. Persist it only in a project-appropriate location when requested or when the task clearly calls for a durable artifact.

## Boundaries

- Specify what should be true, not the code-level implementation plan; hand off to `implementation-plan` when planning is needed.
- Do not implement, edit application code, run migrations, commit, or deploy.
- Do not invent product behavior. Surface material ambiguity; label reasonable inferences.
- Skip formal specification for trivial changes and routine bug fixes unless the user asks for SDD.
- Do not make user confirmation a ritual: ask only when an unresolved choice materially changes behavior, scope, risk, or acceptance.

## Acceptance criteria

- Requirements describe observable user or system behavior rather than vague quality goals.
- Each acceptance criterion can be checked and is traceable to the request, supplied evidence, or an explicitly labeled assumption.
- Scope boundaries, meaningful edge cases, and unresolved decisions are visible.
- The artifact is concise enough to pass to planning without copying unrelated repository context.
- The workflow makes no implementation changes.

## Validation approach

Test with one real feature request and near-miss prompts such as a trivial bug fix, an already specified implementation task, and a request for implementation planning only. Record where automatic activation is appropriate, whether the resulting spec is evidence-grounded and checkable, and whether it duplicates the implementation plan.
