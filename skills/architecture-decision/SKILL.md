---
name: architecture-decision
description: Compare technologies or architecture options against a project's concrete requirements and produce a concise decision record. Use when a material design choice is unresolved; not for implementing an already chosen stack.
---

# Architecture Decision

## Trigger

Use when a feature or project requires a consequential choice among technologies, system boundaries, data stores, or integration patterns. Skip when the project already has a governing decision or the choice is routine and reversible.

## Purpose and inputs

Turn requirements and repository/operational context into an evidence-based decision brief or ADR. Use the feature spec, project instructions, architecture map, existing constraints, and candidate options supplied or discovered.

## Workflow

1. State the decision to make and why it matters now.
2. Collect only decision-relevant requirements: product behavior, team capability, existing stack, deployment, security, data, cost, reliability, and client constraints where evidenced.
3. Separate hard constraints from preferences and unknowns. Ask only about unknowns that materially change the recommendation.
4. Compare a small, credible set of options against the same criteria; show tradeoffs, migration/interoperability cost, and lock-in.
5. Verify time-sensitive claims against current primary documentation when browsing is available; distinguish measured facts from estimates and assumptions.
6. Recommend an option with rationale, consequences, risks, and conditions that would trigger revisiting it. Persist an ADR only in the project's established location or when requested.

## Validation rules

- Recommendation follows from explicit project criteria, not popularity or unsupported scale assumptions.
- Material risks, operating costs, and migration consequences are visible.
- Product, legal, financial, or client-specific rules are not inferred from the word “ERP.”

## Failure conditions

If a missing requirement could reverse the decision, present the tradeoff and ask a focused question instead of manufacturing certainty.

## Expected output

Decision; context/constraints; criteria; compared options; recommendation; consequences/risks; assumptions; and revisit signals.

## Boundaries

This skill evaluates and records architecture choices. It does not change code, install technologies, or override a user's explicit decision.
