# Skill Spec: change-documentation

**Status:** Draft, not yet validated

## Problem and users

Code changes can leave API references, user guides, deployment notes, or operator runbooks stale, while indiscriminate documentation churn creates noise.

## Inputs and output

Input: spec, diff, affected interfaces/operations, repository doc map and language policy. Output: a minimal set of docs to update, actual edits when requested as part of the change, or a clear reason none are needed.

## Boundaries

Do not fabricate behavior, duplicate source code, translate without audience/policy basis, or change unrelated docs. Changelog entries belong to `changelog-maintenance`.

## Acceptance and validation

Docs accurately describe shipped/current behavior and match project/client language policy. Trial on ERP changes with user-facing and internal/operational impact; record omissions and unnecessary edits.
