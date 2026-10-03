# Skill Spec: code-review

**Status:** Draft, not yet validated

## Problem and users

Authors and reviewers need an independent, evidence-based pass that finds consequential bugs and regressions without turning style preferences into findings.

## Inputs and output

Input: diff/branch, base revision, relevant spec/context, and project review conventions. Output: prioritized actionable findings with locations, impact, and supporting evidence, or an explicit no-findings statement with review scope.

## Boundaries

Review only; do not edit/fix, run destructive actions, or assume intended behavior beyond supplied requirements and code evidence. Avoid reporting hypothetical issues without a credible path to impact.

## Acceptance and validation

Findings are reproducible, actionable, non-duplicative, and ordered by severity. Trial on a real change with known seeded issues or maintainer review; record missed/false-positive findings and scope reviewed.
