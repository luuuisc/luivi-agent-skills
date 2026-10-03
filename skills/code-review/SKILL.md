---
name: code-review
description: Review a diff or branch for concrete correctness, security, and regression risks against its requirements. Use for review before merge; not to implement or refactor the change.
---

# Code Review

## Trigger

Use when the user asks for a review or requests an independent review of a change. Review changed behavior, not unrelated repository issues.

## Purpose and inputs

Find actionable defects using the diff, base revision, feature specification, relevant code, tests, and project-specific review rules.

## Workflow

1. Confirm the review target and base; inspect the diff and relevant surrounding code.
2. Trace changed behavior through callers, data flow, error paths, and affected tests as needed.
3. Check correctness, regressions, security boundaries, data integrity, and compatibility relevant to this change.
4. Validate candidate findings against code paths and available tests. Do not fix findings unless separately asked.
5. Report only actionable issues, ordered by severity, with file/line, conditions, impact, and evidence. If none are found, state the review scope and limits.

## Validation rules

- A finding identifies a concrete failure scenario and why the diff causes it.
- Avoid style-only comments, duplicates, speculative risks, and issues outside the review scope.
- Verify line locations against the current diff; distinguish unverified concerns from confirmed defects.

## Failure conditions

If the base, expected behavior, or diff cannot be determined, state the gap and limit conclusions rather than guessing.

## Expected output

Prioritized findings with precise locations and evidence, followed by concise scope/verification limitations.

## Boundaries

Read-only review. Do not modify code, stage files, commit, open PRs, or merge.
