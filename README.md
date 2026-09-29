# Luivi Agent Skills

Reusable engineering workflows that help coding agents do focused work with less repeated context.

Licensed under the [MIT License](LICENSE).

This repository is being built in the open as a practical engineering system for teams using coding agents such as Codex, Claude Code, OpenCode, and Cursor. It focuses on reliable repository understanding, implementation planning, testing, code review, and pre-merge work; host-specific compatibility is being documented and verified incrementally.

The project uses a spec-driven workflow: define the problem and acceptance criteria, implement the smallest useful workflow, try it on real engineering work, record what happened, then improve it. Skills are designed for progressive disclosure: short discovery metadata, focused instructions when relevant, and supporting material only when needed. The goal is useful signal and less repeated discovery, not minimizing tokens at the expense of quality.

## Current status

The first workflow, [`repo-context`](skills/repo-context/SKILL.md), creates a concise Repository Context Map before implementation. The maintainer reports that it worked in a separate CRM repository task; the result was not saved, so a repeatable evaluation is still needed before calling the skill production-ready.

## Roadmap

1. `repo-context` — understand a repository before changing it.
2. `implementation-plan` — turn repository context and a task into an executable plan.
3. `test-strategy` — define and run an appropriate verification strategy.
4. `code-review` — find actionable correctness and regression risks.
5. `pre-merge` — confirm a change is ready to merge.

## Repository map

```text
AGENTS.md                  Repository-specific contributor instructions
skills/                    Canonical reusable skill packages
docs/PROJECT_SPEC.md       Product scope and architecture decisions
docs/validation/           Real-world validation notes
CONTRIBUTING.md            How to propose and validate changes
LICENSE                    MIT License
```

See [`docs/PROJECT_SPEC.md`](docs/PROJECT_SPEC.md) for the current product spec and the proposed cross-agent architecture. This project does not yet include an installer or claim full behavior parity across agent tools.

## Contributing

Start with [CONTRIBUTING.md](CONTRIBUTING.md) and the repository [AGENTS.md](AGENTS.md). Keep each skill focused on one repeatable engineering problem and capture evidence from real use before marking it usable.
