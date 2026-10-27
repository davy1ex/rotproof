# RotProof

[**EN 🇺🇸**](README.md) · [RU 🇷🇺](README.ru.md)

**Build with AI. Prove you understand it.**

RotProof is a portable kit for AI-assisted development. It helps you keep the project understandable as generated code accumulates: agree on decisions, break work into verifiable slices, and check explanations against the source.

![RotProof meme: a developer guides a muzzled AI agent through an architecture diagram.](assets/rotproof-readme-meme.en.png)

## Quick start: let an AI agent fetch RotProof

Give the agent the repository URL and ask it to clone RotProof into a new folder. Then send this prompt and fill in your goal:

```text
RotProof Git repository: https://github.com/davy1ex/rotproof.git

Clone or download this repository into a new directory so you can inspect it. Do not overwrite an existing checkout. Read README.md, README.ru.md, AGENTS.md, USE_CASES.md, docs/, and prompts/.

Explain what RotProof is for, choose the use case that fits my target, and tell me the exact next step and prompt. If the target is unclear, ask one clarifying question.

For now, only orient me: do not edit files, run project commands, or commit. If you cannot clone the repository because of access restrictions, tell me what access or local copy you need. Do not claim to have read files you could not access.

My target: <new project / existing project URL or local path / not decided yet>
```

To apply RotProof to another project, include that project's URL or local path and say whether it is new or already contains code.

## Quick start for a new project

1. Copy `AGENTS.md` into the project root and `docs/` into its documentation directory.
2. Keep `prompts/`, `USE_CASES.md`, and `checklists/` somewhere you and the team can access.
3. Draft the product brief with [`prompts/draft-product.md`](prompts/draft-product.md). Once approved, put the agreed text in `docs/PRODUCT.md`.
4. Run [`prompts/initialize-project.md`](prompts/initialize-project.md) to map the project and propose its first vertical slice.
5. Approve the scope and acceptance criteria, then use [`prompts/implement-approved-slice.md`](prompts/implement-approved-slice.md).

To adopt RotProof in an existing project, start with [`prompts/adopt-existing-project.md`](prompts/adopt-existing-project.md). It inventories current rules and documents without overwriting them.

## Working cycle

1. The agent studies the rules, documents, code, and Git status.
2. The agent proposes a scenario, boundaries, acceptance criteria, and open decisions without changing files.
3. You approve the approach and decisions that belong to you.
4. The agent implements only the approved slice, reviews the diff, and reports the checks it actually ran.
5. You accept the result and separately decide whether to commit, merge, or publish it.

See [`USE_CASES.md`](USE_CASES.md) for the workflows.

## Prompts and workflows

The linked templates and prompts are currently written in Russian.

- [Start a new project](prompts/initialize-project.md)
- [Adopt RotProof in an existing project](prompts/adopt-existing-project.md)
- [Plan a feature](prompts/propose-feature.md)
- [Plan a refactor](prompts/propose-refactor.md)
- [Plan a roadmap without implementation](prompts/plan-roadmap.md)
- [Draft PRODUCT.md](prompts/draft-product.md)
- [Check your understanding of the project](prompts/check-project-understanding.md)
- [Implement an approved slice](prompts/implement-approved-slice.md)

## Product and PRD

`docs/PRODUCT.md` is the source of truth for product goals, users, value, and boundaries. A feature PRD is optional: use [`docs/FEATURE-PRD-TEMPLATE.md`](docs/FEATURE-PRD-TEMPLATE.md) when a feature needs more detail than one scenario and its acceptance criteria. A PRD elaborates on `PRODUCT.md`; it does not duplicate it.

## Skills

You do not need a separate skill to get started. `AGENTS.md` provides the project's standing rules, and the prompts start individual workflows. If you later want to invoke a workflow with a short command across multiple projects, you can add a skill as a thin wrapper around this kit without creating a second source of rules.

## Customize for your project

Replace placeholders with information confirmed by you. Set `Draft`, `Proposed`, and `Accepted` according to the actual decision status. Do not add technology choices, contracts, or architecture constraints to the templates without a separate decision.
