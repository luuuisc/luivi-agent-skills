---
name: pr-readiness
description: Prepare a review-ready pull request title, English description, and evidence checklist from a completed change. Use before opening a PR; do not open or publish it unless asked.
---

# PR Readiness

## Trigger

Use when a completed branch is being prepared for review or the user asks whether/how to open a PR. Do not use for implementation planning or post-review merge readiness.

## Purpose and inputs

Create a truthful reviewer handoff from the user request/spec, diff and commits, test results, changelog/docs updates, and repository PR template/policy.

## Workflow

1. Confirm base/head and inspect the full diff, commit list, and working-tree state.
2. Check scope alignment with the spec, verification evidence, relevant docs/changelog, and secrets or unrelated files.
3. Read the repository PR template and contribution policy. Draft an English title and body covering why, what, evidence/checks, risks, and known limitations.
4. Treat unavailable checks or review dependencies as outstanding; never claim they passed.
5. Report ready/not-ready, blockers, and the proposed title/body. Create the PR only if the user explicitly asked and the required remote/auth tools are available.

## Validation rules

- Narrative accurately reflects the diff and accepted behavior.
- English is used for PR title and description; customer-facing material follows its own locale policy.
- Test claims cite observed outcomes; no credentials or customer data are exposed.

## Failure conditions

If the base/diff or test evidence cannot be confirmed, state the limit and do not present the PR as fully ready.

## Expected output

Readiness verdict, blockers, and an English PR title/body with verified checks and explicit gaps.

## Boundaries

Drafting does not authorize pushing, opening a PR, assigning reviewers, or changing remote state. Perform those actions only when explicitly requested.
