# Skill Spec: changelog-maintenance

**Status:** Draft, not yet validated

## Problem and users

Customers and maintainers need an accurate, audience-appropriate history of meaningful changes, kept current with the implementation.

## Inputs and output

Input: accepted feature/spec, diff, tests, existing changelog format and project/client language policy. Output: concise entry under the appropriate unreleased/version section, or a documented no-entry rationale.

## Boundaries

Never invent changes, expose private data, rewrite historical releases, or infer client language. Do not claim this skill alone guarantees automatic updates on every change; the project instruction/PR checklist must enforce the checkpoint.

## Acceptance and validation

Entry matches actual user-visible impact and existing format/language; historical sections remain intact. Trial on ERP changes with and without user-visible behavior; record correct entries, misses, and false additions.
