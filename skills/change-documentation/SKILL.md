---
name: change-documentation
description: Identify and update technical or user documentation affected by a behavior, API, configuration, or operations change. Use during implementation; changelog entries are handled separately.
---

# Change Documentation

## Trigger

Use when a change may alter user guidance, API/configuration contracts, deployment, support, or operational procedures. Skip when the diff has no documentation impact and the user did not request docs.

## Purpose and inputs

Keep only the docs necessary to explain current behavior accurate. Use the feature spec, diff, existing docs, and repository/client language policy.

## Workflow

1. Identify affected audiences and docs from repository structure, links, and project instructions.
2. Determine whether behavior, setup, API, security, support, or operations guidance changes; distinguish required updates from optional polish.
3. Update the smallest authoritative docs location when documentation changes are within task scope. Use the configured audience language; ask if materially unclear.
4. Check examples, links, terminology, and claims against implementation and tests. Do not document unimplemented future behavior as current.
5. Report files changed or why no docs update was warranted. Route release-history entries to `changelog-maintenance`.

## Validation rules

- Statements match implemented behavior and project policy.
- One source of truth is preferred over duplicate documentation.
- Customer-facing and internal technical content use their configured language/audience.

## Failure conditions

If the client/audience language or behavior cannot be established, state the gap and avoid publishing assumptions as fact.

## Expected output

Affected audience/docs, concise edits or no-change rationale, and verification of examples/links where relevant.

## Boundaries

Do not alter application behavior, rewrite unrelated documentation, invent client requirements, or create release-history entries handled by `changelog-maintenance`.
