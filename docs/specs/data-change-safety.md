# Skill Spec: data-change-safety

**Status:** Draft, not yet validated

## Problem and users

Schema and bulk data changes can cause downtime, irreversible data loss, tenant leakage, or broken old/new application versions.

## Inputs and output

Input: data change, schema/current behavior, deployment topology, data criticality, tenancy model, and operational constraints. Output: compatibility/safety assessment, staged migration and validation plan, rollback/forward-repair options, and explicit unknowns.

## Boundaries

Do not execute destructive or production migrations, invent business/accounting/tax policies, or assume backup/restore works. Require explicit authorization for production-impacting operations.

## Acceptance and validation

Plan considers expand/migrate/contract compatibility as applicable, tenant isolation, integrity checks, locking/downtime, backup/restore evidence, and recovery. Trial on a non-production ERP migration; record risks surfaced and false assurances.
