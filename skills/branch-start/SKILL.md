---
name: branch-start
description: Prepare a safe feature or fix branch by checking Git state, base, and repository naming policy. Use when beginning implementation; not for reviewing or merging an existing branch.
---

# Branch Start

## Trigger

Use when implementation is about to begin and the user or project workflow expects work on a dedicated branch.

## Purpose and inputs

Choose or create a branch consistent with the task, repository policy, current branch/base, and working-tree state.

## Workflow

1. Read branch naming and base-branch policy from repository instructions or recent Git history; do not impose a universal scheme.
2. Inspect current branch, working-tree state, and whether a requested branch already exists.
3. Recommend the branch name and base. If the task clearly requests implementation and branch creation is the project convention, create only a new branch from the confirmed base.
4. If there are uncommitted changes, an unexpected branch, a conflicting branch name, or uncertain base, preserve state and ask before switching or reusing.
5. Confirm the resulting branch and report any preserved working changes.

## Validation rules

- Never lose, overwrite, or silently strand existing work.
- Branch name and base follow observed project policy or are labeled proposals.
- Confirm the actual branch after any creation.

## Failure conditions

If Git state cannot be read or the base/policy is ambiguous and consequential, stop before changing branches.

## Expected output

Current state; proposed/created branch and base; policy evidence; and remaining action or blocker.

## Boundaries

Do not reset, clean, force-switch, delete branches, or commit. Ask before switching to an existing branch or taking any action that could affect uncommitted work.
