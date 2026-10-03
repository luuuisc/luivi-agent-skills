# Skill Spec: commit-craft

**Status:** Draft, not yet validated

## Problem and users

Commits should form reviewable units and explain intent accurately without mixing unrelated changes or hiding scope.

## Inputs and output

Input: staged/unstaged diff, task/spec, commit conventions, and requested commit scope. Output: suggested commit boundaries and precise English commit messages, or commits only when explicitly requested.

## Boundaries

Never stage all files blindly, include secrets/generated files unintentionally, amend/rewrite published history, or commit without user authorization. Client-facing language policy does not change the English commit-message requirement.

## Acceptance and validation

Each proposed commit is cohesive and matches its diff; message follows observed convention and states intent. Trial on a real ERP change; record whether boundaries/messages aided review and whether files were omitted or included incorrectly.
