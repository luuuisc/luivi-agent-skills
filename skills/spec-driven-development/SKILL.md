---
name: spec-driven-development
description: Turn a new or materially changed feature request into a concise, testable specification before implementation. Use when desired behavior or acceptance criteria need definition; not for implementation planning alone, trivial fixes, or an already specified feature.
---

# Spec-Driven Development

## Trigger

Use when the user wants to define or build a feature and the desired behavior, scope, or acceptance criteria need to be made explicit before planning implementation. Skip for trivial changes, routine bug fixes, or a feature whose specification is already clear unless the user requests this workflow.

## Purpose

Produce a compact `Feature Specification` that captures what should be true and can be handed to implementation planning without repeating repository discovery.

## Inputs

- User's requested outcome, constraints, preferences, and decisions.
- Applicable project instructions and any supplied issue, design, or product references.
- A current `Repository Context Map` when repository behavior or constraints affect the specification; otherwise inspect only evidence needed to ground relevant requirements.

## Workflow

1. Restate the user/problem outcome in behavioral terms. Separate explicit decisions from assumptions and proposed solutions.
2. Reuse current project context where available. Inspect only task-relevant evidence; identify which requirements are grounded in the request, project behavior, or supplied references.
3. Define scope, non-goals, key user/system scenarios, and observable acceptance criteria. Include edge cases only when they materially affect behavior or verification.
4. Surface unknowns. Ask a concise question only when an unresolved choice could materially change scope, behavior, risk, or acceptance. Otherwise state a reasonable, reversible assumption explicitly.
5. Produce a concise `Feature Specification`. Keep implementation design and task sequencing for the `implementation-plan` workflow.
6. Persist the spec in the project's established location only when the user requests a durable artifact or the task clearly requires one. Do not invent a new spec directory convention without evidence.
7. If implementation is also requested, hand the spec to implementation planning when available; do not duplicate the plan inside the spec.

## Validation rules

- Requirements are behavioral and traceable to the user request, project evidence, supplied references, or a labeled assumption.
- Acceptance criteria are observable and checkable; replace vague terms such as “fast,” “intuitive,” or “robust” with measurable conditions when the evidence allows.
- Scope, non-goals, important scenarios, and material unresolved decisions are explicit.
- Reused repository context is not recopied wholesale; cite only relevant files or facts.
- The spec avoids prescribing architecture or implementation details unless the user has made them constraints.

## Failure conditions

If the requested outcome cannot be determined, or a product decision would materially change the specification, provide the grounded partial spec and ask only the blocking question. If project behavior is essential but cannot be inspected or established, label the gap instead of fabricating requirements.

## Expected output

Return a `Feature Specification` with:

- **Outcome** — user or system behavior being improved.
- **Scope / non-goals** — what is and is not covered.
- **Requirements** — observable behavior, grouped only as needed.
- **Scenarios and acceptance criteria** — checkable success conditions.
- **Assumptions / open questions** — only those that can affect the result.
- **Evidence** — concise references to the request, project files, or supplied material.

Keep it proportional to the feature. Include no generic implementation plan. When useful, end with a short handoff note for `implementation-plan`.

## Boundaries

- This workflow specifies; it does not implement, edit application code, run migrations, commit, or deploy.
- Do not force a formal spec onto a trivial task or a well-specified request.
- Do not invent user intent or require confirmation for immaterial, reversible details.
- Explicit user instructions take precedence over this workflow.
