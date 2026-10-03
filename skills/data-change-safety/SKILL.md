---
name: data-change-safety
description: Assess schema migrations or bulk data changes for integrity, compatibility, tenant isolation, downtime, and recovery risks. Use for consequential data changes; not for routine reads or unrelated code review.
---

# Data Change Safety

## Trigger

Use when a task changes persisted schema, transforms existing records, backfills data, or changes tenant/data boundaries. A normal code review may surface a risk, but this skill performs a focused data-change assessment.

## Purpose and inputs

Produce a safe, evidence-based plan using the change/spec, schema and data access patterns, deployment/version topology, tenancy model, project policies, and verified operational capabilities.

## Workflow

1. Map affected tables/entities, readers/writers, constraints, indexes, tenant keys, and data volume only from repository or operator evidence.
2. Identify integrity, privacy/tenant isolation, locking/downtime, old/new version compatibility, retries/idempotency, and partial-failure risks.
3. Propose staged migration/backfill/validation and rollback or forward-repair options appropriate to the actual deployment model; state assumptions.
4. Verify whether backups, restore drills, staging data, and observability exist. Never equate a configured backup with a proven restore.
5. Define preconditions, data invariants, validation queries/checks, stop signals, and recovery ownership.
6. Surface business decisions (including accounting, taxes, retention, and customer-specific rules) for the domain owner; do not infer them.

## Validation rules

- Each risk and safety check is grounded in schema, code, deployment, or explicitly labeled operator input.
- Plan handles partial completion and compatibility where relevant.
- Production/destructive steps are separated and require explicit authorization.

## Failure conditions

If data volume, tenancy, migration tooling, recovery, or domain semantics are unknown and could alter safety, stop at a partial assessment and ask for evidence or ownership.

## Expected output

Affected data paths; risks; staged plan; integrity/tenant checks; recovery approach and evidence; required approvals; and unresolved questions.

## Boundaries

This skill assesses and plans. It does not execute production migrations, delete/overwrite customer data, or decide client business/legal policy.
