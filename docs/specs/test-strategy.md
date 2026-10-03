# Skill Spec: test-strategy

**Status:** Draft, not yet validated

## Problem and users

Implementers need a risk-based way to decide what to test and to report meaningful verification without running every test or overstating results.

## Inputs and output

Input: task/spec, repository instructions, changed files or proposed plan, existing tests and commands. Output: a concise verification plan and evidence report listing checks run, results, skipped checks, and remaining risk.

## Boundaries

Do not invent commands, edit production code, or claim a test passed without observed output. Add or change test code only when the user requested implementation and that test is in scope. Preserve environment and data; avoid destructive or production tests without explicit authorization.

## Acceptance and validation

Checks map to acceptance criteria and change risk; existing narrow tests precede broader suites where appropriate; failures are distinguished from environment/setup issues. Trial on a real ERP feature and record request/spec, selected checks, actual outcomes, omissions, and whether the plan caught relevant risk.
