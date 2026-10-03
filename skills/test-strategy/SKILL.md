---
name: test-strategy
description: Choose and run proportionate verification for a planned or completed code change, then report observed evidence and remaining risk. Use for test selection or verification; not for implementing the feature itself.
---

# Test Strategy

## Trigger

Use when deciding how to verify a planned/completed change or when asked to run/report tests. Do not activate for unrelated test-framework design.

## Purpose and inputs

Map the requested behavior and change risk to repository-supported checks. Use the task/spec, project instructions, changed files, and existing test commands as evidence.

## Workflow

1. Identify acceptance criteria and the code paths or risks they exercise.
2. Inspect test conventions and confirm commands from project files or prior evidence; distinguish known commands from suggestions.
3. Select the smallest meaningful checks first, expanding scope for integration, migrations, security boundaries, or broad changes.
4. Run only checks within the user's authorization and safe environment. Do not use production data or destructive commands without explicit authorization.
5. Report exact checks and observed results, failures, skipped checks with reasons, and residual risk. If asked only for a plan, do not run tests.

## Validation rules

- Each check maps to an acceptance criterion or identified risk.
- Report observed output accurately; a started or timed-out test is not a pass.
- Separate test failure, flaky behavior, and environment/setup failure when evidence supports it.

## Failure conditions

If test commands or required environment are unknown, inspect supported project configuration and state the gap. Do not invent commands, credentials, test fixtures, or a pass verdict.

## Expected output

Concise verification plan or report: criterion/risk, check, result, skipped items, and remaining risk.

## Boundaries

This skill selects and runs verification; it does not implement feature code or weaken tests to obtain a pass. Test-file edits are only in scope when the user requested implementation and they are necessary to verify it.
