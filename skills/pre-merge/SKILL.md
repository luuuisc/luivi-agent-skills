---
name: pre-merge
description: Determine whether a reviewed pull request is ready to merge by checking required evidence, approvals, CI, conflicts, and project policy. Use for final readiness; do not merge or bypass gates.
---

# Pre-Merge

## Trigger

Use when asked whether a PR/change is ready to merge or to perform a final pre-merge check.

## Purpose and inputs

Assess readiness against the project's merge policy, task acceptance criteria, current diff/PR state, CI, review status, and relevant test/documentation evidence.

## Workflow

1. Identify the exact PR/change and target branch.
2. Read repository merge requirements and inspect live check/review/conflict state when tools permit.
3. Verify acceptance criteria, test evidence, unresolved feedback, documentation/changelog obligations, and scope.
4. Treat missing, stale, or inaccessible evidence as unknown, not passed. Distinguish required gates from recommendations.
5. Return a clear ready/not-ready/undetermined verdict with blockers and evidence.

## Validation rules

- Every verdict is traceable to observable current evidence or explicitly labeled unknown.
- Do not report stale CI or approvals as current.
- Surface any mismatch between project policy and available state.

## Failure conditions

If PR state, policy, or required checks are inaccessible, explain which readiness items remain unverified.

## Expected output

Verdict; blockers; verified gates; unknowns; and the smallest next action to reach readiness.

## Boundaries

This skill assesses readiness only. It does not merge, force-push, dismiss reviews, waive checks, or edit the PR unless the user separately requests that action.
