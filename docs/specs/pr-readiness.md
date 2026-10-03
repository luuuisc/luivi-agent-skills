# Skill Spec: pr-readiness

**Status:** Draft, not yet validated

## Problem and users

Reviewers need a complete, truthful English PR handoff that connects motivation, requirements, implementation, tests, risks, and docs.

## Inputs and output

Input: spec/task, diff/commits, test evidence, changelog/docs status, base branch and PR template. Output: readiness verdict plus English title/body/checklist; create the PR only when explicitly requested.

## Boundaries

Do not open a PR, push, or change labels/reviewers unless requested. Never claim checks passed without evidence or include secrets/client data.

## Acceptance and validation

PR narrative matches actual diff and includes meaningful verification/limitations, with English title/body. Trial against real ERP changes; capture reviewer clarity and missing/false claims.
