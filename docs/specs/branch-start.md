# Skill Spec: branch-start

**Status:** Draft, not yet validated

## Problem and users

Starting feature work on an incorrect base or switching away from dirty work can cause lost effort and confusing reviews.

## Inputs and output

Input: approved task/spec/plan, current Git state, branch policy, and target base. Output: reuse/create recommendation, branch name, base, and any state that must be resolved first.

## Boundaries

Never discard work, force-reset, or silently switch branches. Create a branch only when implementation is requested and policy/state make the action clear; ask when existing work or base selection is ambiguous.

## Acceptance and validation

Branch choice follows repository convention and correct base; dirty state is preserved. Trial on an ERP feature with clean and dirty-state cases; record actions and safety outcomes.
