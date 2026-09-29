# Project Spec: Portable Engineering Workflows for Coding Agents

**Status:** Draft, V0
**Last updated:** 2026-09-29

## Problem

Coding agents can work across repositories, but their results depend on how consistently they discover project context, follow engineering workflows, and validate changes. Users who switch between Codex, Claude Code, OpenCode, and Cursor also face different discovery paths and instruction mechanisms.

This project will build small, evidence-tested workflows that improve engineering work while keeping each tool's integration behavior explicit.

It will also help engineers use long-running and multi-agent workflows without filling every agent's working context with unrelated instructions, repeated repository scans, or verbose handoffs.

## Intended users

- Individual engineers who use more than one coding agent.
- Maintainers who want repeatable development workflows in real repositories.
- Agent builders who need portable, inspectable workflow instructions.

## Product outcome

A public, version-controlled collection of focused engineering skills that an engineer can understand, test on real work, and install or expose to supported coding agents without confusing reusable workflows with project-specific instructions.

The skills should compose through concise inputs and outputs. For example, a `Repository Context Map` should give an implementation-planning workflow enough evidence to proceed without rediscovering the whole repository.

When work is split across agents, each handoff should carry only the task-relevant evidence, decisions, and next action. The orchestration layer assigns ownership and parallel work; individual skills define their own scope and the compact artifacts another agent can consume.

## V0 scope

Build and validate these workflows in order:

1. `repo-context`
2. `implementation-plan`
3. `test-strategy`
4. `code-review`
5. `pre-merge`

Do not start a later workflow until the current one meets its acceptance criteria and has recorded validation evidence. A maintainer-reported real-world success can establish initial usability; distinguish that from a reproducible or independent evaluation.

## Out of scope for V0

- A general-purpose agent framework or prompt collection.
- Claims that different agent products behave identically.
- A complex installer, plugin marketplace, or hosted skill registry before a real distribution need is demonstrated.
- Project-specific business knowledge inside globally reusable skills.
- Token minimization as an end in itself, or claims that skills directly control provider prompt caching.
- Scripts, references, or evaluation infrastructure without a concrete reliability or measurement benefit.

## Proposed architecture

### Canonical skill content

- Keep reusable workflow packages under `skills/<skill-name>/` in this repository.
- Each package starts with `SKILL.md`, using the portable Agent Skills frontmatter (`name` and `description`) and a focused procedure.
- Add scripts, references, assets, or evals only when the skill's tested workflow needs them.
- Keep tool-specific metadata optional and separate from portable workflow requirements.
- Keep discovery metadata concise; load detailed instructions only when relevant, and supporting material only when the active task needs it.
- Make skill inputs and outputs explicit so later skills or agents can reuse compact evidence instead of repeating discovery.
- Prefer high signal per token over the shortest possible instructions. A loaded skill still consumes working context, so it must improve the task enough to justify that cost.

### Agent instructions and project context

- Root `AGENTS.md` governs work on this repository and its contribution process.
- A consuming project's instruction files describe that project's architecture, constraints, and conventions.
- Skills describe reusable workflows loaded for a task.
- Tool-specific instruction files and rules may adapt the same intent to each host, but are not automatically interchangeable.
- Agent orchestration is a separate layer. Skills can define clear task boundaries and handoff artifacts, but a `SKILL.md` alone does not spawn agents or manage their context windows.

### Distribution model

- This Git repository is the source of truth and review surface.
- Initial use can reference a skill by path or place it in a host's supported skills directory.
- Defer an installer until the supported host matrix and repeated setup friction justify one.
- Document local/global paths per host and verify discovery in each host before claiming support.

## Cross-agent compatibility baseline

The shared content will target the open `SKILL.md` Agent Skills format. Discovery is host-specific and must be treated as an integration concern:

| Host | Project skill discovery | User/global skill discovery | Instruction context |
|---|---|---|---|
| Codex | `.agents/skills/` | `$CODEX_HOME/skills/` (normally `~/.codex/skills/`) | `AGENTS.md`, including global and nested project instructions |
| Claude Code | `.claude/skills/` | `~/.claude/skills/` | `CLAUDE.md` and Claude-specific settings |
| OpenCode | `.opencode/skills/`, plus compatible sources | `~/.config/opencode/skills/`, `~/.agents/skills/`, compatible Claude paths | `AGENTS.md`, with documented Claude compatibility |
| Cursor | `.agents/skills/`, `.cursor/skills/`, compatible Claude/Codex paths | `~/.agents/skills/`, `~/.cursor/skills/`, compatible Claude/Codex paths | Cursor Rules and project instructions |

This table is a starting point based on vendor documentation checked on 2026-09-29. Paths and supported metadata can change; verify against each host's current documentation before implementing distribution or publishing compatibility claims.

Sources:

- [Codex: Build skills](https://learn.chatgpt.com/docs/build-skills)
- [Codex: Custom instructions with AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Claude: Agent Skills overview](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- [OpenCode: Agent Skills](https://opencode.ai/docs/skills)
- [Cursor: Skills](https://docs.cursor.com/skills)
- [Agent Skills specification](https://agentskills.io/specification)

## Context efficiency and prompt caching

This project targets context efficiency by reducing irrelevant instructions, repeated discovery, and oversized handoffs. Progressive disclosure makes detailed skill instructions available on demand; once loaded, those instructions still occupy part of the active context. Keep a skill only when the reliability or quality it adds justifies that space.

Prompt caching is a separate provider/runtime optimization. A cached prompt may reduce repeated processing or input cost where the host supports it, but it does not mean the prompt has disappeared from the model's context. Anthropic's context-window documentation explicitly counts cache-read and cache-creation tokens toward the context window; OpenAI usage reports cached tokens as a subset of input tokens. These are API-level details and may not be visible or configurable in every coding-agent product.

Sources:

- [Anthropic: Context windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)
- [Anthropic: Manage tool context](https://platform.claude.com/docs/en/agents-and-tools/tool-use/manage-tool-context)
- [OpenAI: Responses API usage and cached tokens](https://platform.openai.com/docs/api-reference/responses-streaming/response/refusal)

## Acceptance criteria

The repository is ready for its first public release when:

- Its README explains the problem, current status, workflow roadmap, and how to inspect or try a skill.
- Every skill included in a release follows the repository skill standard and has explicit boundaries.
- `repo-context` has at least one recorded real-world trial with task/prompt, outcome, observed gaps, and evidence limitations clearly stated.
- The license and contribution expectations are explicit before inviting outside contributions.
- Public compatibility claims are limited to paths and behaviors that have been verified on the named hosts.
- No secret, private project data, or unreviewed user-specific context is included.
- Each workflow has explicit inputs, outputs, and boundaries that allow orchestration or handoff without reloading unrelated context.
- Context efficiency is evaluated as less repeated discovery and more task-relevant signal, without treating cached tokens as removed from context or sacrificing task quality.

## Current evidence and open decisions

- `repo-context` is usable for initial work based on a successful maintainer-reported trial in a separate CRM repository. The generated map and exact prompt were not saved, so the trial is not reproducible or independently evaluated.
- The maintainer selected the MIT License, and the repository now includes the license text and contribution expectations.
- A public evaluation format, installation workflow, and initial host verification matrix remain to be decided based on actual usage.

## Next slice

Develop and validate `implementation-plan` against a real task. In parallel, review the maintainer's starred repositories for techniques worth testing; treat stars as a reading queue, not an endorsement or dependency list. Revisit `repo-context` with a saved, privacy-reviewed output when setting up measurable evals.
