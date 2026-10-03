---
name: commit-craft
description: Turn a reviewed diff into cohesive commit boundaries and accurate English commit messages that follow repository conventions. Use when preparing commits; not to rewrite published history.
---

# Commit Craft

## Trigger

Use when asked to prepare commits or when a requested implementation needs a commit plan. Do not activate for general code review alone.

## Purpose and inputs

Make commits small enough to review and complete enough to represent a coherent change. Use the task/spec, repository commit conventions, staged and unstaged diff, and untracked file list.

## Workflow

1. Inspect status and diffs before staging. Identify unrelated edits, generated files, and likely secrets.
2. Read the repo's commit convention; if none exists, propose a concise conventional style without pretending it is established policy.
3. Group changes by coherent behavior and dependencies. Explain when a single atomic commit is safer than splitting.
4. Draft accurate English messages that describe actual intent and scope; never claim tests or behavior not evidenced by the diff/results.
5. Stage only files the user authorized. Before committing, show/check staged diff and confirm authorization if the request did not clearly include making commits.
6. After a commit, verify its contents and report the hash/message.

## Validation rules

- Each message matches its staged diff and is written in English.
- No unrelated, unreviewed, or secret files are included.
- Never amend/rebase/force-push already published history without explicit instruction.

## Failure conditions

If ownership of dirty files, intended scope, or authorization to commit is unclear, do not stage/commit those files; report the ambiguity.

## Expected output

Commit grouping and proposed messages, followed by verified commit identifiers if commits were authorized and created.

## Boundaries

Do not push, amend, rebase, or rewrite history unless the user explicitly requests the exact action. English is required for commit messages; follow project policy for code and customer-facing text separately.
