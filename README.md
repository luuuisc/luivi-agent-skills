# Luivi Agent Skills

Reusable engineering workflows that help coding agents do focused work with less repeated context.

Licensed under the [MIT License](LICENSE).

This repository is being built in the open as a practical engineering system for teams using coding agents such as Codex, Claude Code, OpenCode, and Cursor. It focuses on reliable repository understanding, implementation planning, testing, code review, and pre-merge work; host-specific compatibility is being documented and verified incrementally.

The project uses a spec-driven workflow: define the problem and acceptance criteria, implement the smallest useful workflow, try it on real engineering work, record what happened, then improve it. Skills are designed for progressive disclosure: short discovery metadata, focused instructions when relevant, and supporting material only when needed. The goal is useful signal and less repeated discovery, not minimizing tokens at the expense of quality.

The differentiation we are testing is not a larger catalog: each workflow should earn its place with real-task evidence, a compact artifact that can be handed to another workflow or agent, and explicit quality boundaries. Context efficiency should show up as less repeated discovery and smaller task-relevant handoffs without worse engineering outcomes.

## Current status

[`repo-context`](skills/repo-context/SKILL.md) and [`implementation-plan`](skills/implementation-plan/SKILL.md) are usable for initial work based on maintainer-reported trials; neither has a complete, independently reviewed evaluation record. The remaining skills are drafts and should be validated against real tasks before being described as usable.

## Install

The skills are organized as `skills/<skill-name>/SKILL.md` and are intended to be installable with the open-source [`skills` CLI](https://github.com/vercel-labs/skills). No repository-specific installer is required.

List skills available in this repository:

```sh
npx skills add luuuisc/luivi-agent-skills --list
```

Install one skill into the current project for Codex:

```sh
npx skills add luuuisc/luivi-agent-skills --skill repo-context --agent codex --copy --yes
```

Install every skill in this repository into the current project for Codex, including drafts you can try and evaluate:

```sh
npx skills add luuuisc/luivi-agent-skills --skill '*' --agent codex --copy --yes
```

Install that skill globally for Claude Code instead:

```sh
npx skills add luuuisc/luivi-agent-skills --skill repo-context --agent claude-code --global --copy --yes
```

Replace `repo-context` with another skill name and `codex` or `claude-code` with a supported agent identifier. Project installation is the default; `--global` targets the user's agent skill directory. The CLI may support additional agents and install methods; consult its [current documentation](https://www.skills.sh/docs/cli). Installing a skill makes it discoverable, but does not imply that the skill has passed this repository's real-work validation.

These commands are documented against the CLI interface but have not yet been successfully exercised from a clean environment. Cross-agent discovery and behavior are verified separately and are not implied by installability.

After installation, describe the outcome in normal language; you should not need to provide a file path or skill name when the agent supports automatic skill discovery. The agent uses each skill's name and short `description` to decide which instructions are relevant. Keep descriptions specific and non-overlapping; activation behavior can still differ across agents. For Codex, see the [official OpenAI skill documentation](https://developers.openai.com/api/docs/guides/tools-skills).

## Roadmap

1. `repo-context` — understand a repository before changing it.
2. `spec-driven-development` — turn a feature request into a testable behavior specification.
3. `implementation-plan` — turn repository context and a specification/task into an executable plan.
4. `test-strategy` — define and run an appropriate verification strategy.
5. `code-review` — find actionable correctness and regression risks.
6. `pre-merge` — confirm a change is ready to merge.

Additional skills in the draft catalog: `architecture-decision`, `branch-start`, `commit-craft`, `change-documentation`, `changelog-maintenance`, `pr-readiness`, and `data-change-safety`. They are optional task-specific workflows, not steps to load on every change.

## Repository map

```text
AGENTS.md                  Repository-specific contributor instructions
skills/                    Canonical reusable skill packages
docs/PROJECT_SPEC.md       Product scope and architecture decisions
docs/specs/                Per-skill problem statements and acceptance criteria
docs/validation/           Real-world validation notes
CONTRIBUTING.md            How to propose and validate changes
LICENSE                    MIT License
```

See [`docs/PROJECT_SPEC.md`](docs/PROJECT_SPEC.md) for the current product spec, distribution decision, and proposed cross-agent architecture. This project does not claim full behavior parity across agent tools.

## Contributing

Start with [CONTRIBUTING.md](CONTRIBUTING.md) and the repository [AGENTS.md](AGENTS.md). Keep each skill focused on one repeatable engineering problem and capture evidence from real use before marking it usable.
