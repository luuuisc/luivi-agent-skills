---
name: changelog-maintenance
description: Update a project's changelog from verified user-visible changes, following its format and audience-language policy. Use before PR/release for meaningful behavior changes; not for routine refactors with no external impact.
---

# Changelog Maintenance

## Trigger

Use before a PR/release when a change affects users, operators, APIs, compatibility, or security, or when the user asks to update the changelog. Skip entries for internal-only changes unless project policy requires them.

## Purpose and inputs

Keep release history concise and grounded in shipped behavior. Use the accepted spec, actual diff, verification results, existing changelog format, and project/client audience-language policy.

## Workflow

1. Inspect the existing changelog and release process; follow established headings and placement.
2. Identify externally meaningful changes from the spec and diff. Categorize using the repository's convention; do not add a new taxonomy unnecessarily.
3. Write an entry describing user impact, not internal implementation details. Use the configured audience language. Keep commits and PR content in English when project policy requires that, independently of customer-facing release language.
4. Place the entry in the existing Unreleased/next-release section when present. If no format exists, propose one before creating a new file unless the user asked you to establish it.
5. Verify claims against implementation and test evidence. Do not include secrets, customer data, or unshipped work; do not modify released history.
6. If no entry is warranted, state why. For consistency across all relevant changes, rely on the repository's contributor instructions or PR checklist to require this review; this skill alone is not an enforcement mechanism.

## Validation rules

- Every entry is supported by a real user/operator-visible change.
- Audience, language, and format match project policy.
- Historical release entries remain unchanged.

## Failure conditions

If release format, audience, or language is unknown and materially changes the result, ask or record a minimal proposal instead of silently assuming.

## Expected output

Changelog path/section and entry, or a concise no-entry rationale, with any policy gap called out.

## Boundaries

Do not fabricate release notes, edit application code, expose private/customer data, or claim that the changelog will always be updated without a project-level required check.
