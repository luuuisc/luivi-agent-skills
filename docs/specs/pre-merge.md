# Skill Spec: pre-merge

**Status:** Draft, not yet validated

## Problem and users

Before merging, contributors need a final evidence-based check that review, CI, requirements, documentation, and repository state are ready.

## Inputs and output

Input: PR/change, target branch, acceptance criteria, CI/review state, and project merge policy. Output: ready/not-ready verdict, blockers, and exact evidence/gaps.

## Boundaries

Read-only readiness check. Never merge, bypass checks, dismiss review, or modify PR state unless separately and explicitly asked. Do not treat unknown status as success.

## Acceptance and validation

Verdict accounts for required checks, unresolved review comments, conflicts, test evidence, docs/changelog policy, and scope. Trial on a real PR; record conditions detected/missed and false-ready risks.
