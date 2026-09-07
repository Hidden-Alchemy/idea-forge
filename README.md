# Idea Forge

> AI-assisted idea-to-system pipeline tool — walks a rough idea through Hidden
> Alchemy's own stages (spec drafting, feasibility, architecture sketching,
> system scaffolding), with a human decision at every transition.

**Status:** `concept` — the pipeline Promise early research is done and the go
decision is recorded; no runnable software exists yet. This status is earned
upgrade, not assumed. Last updated: 2026-09-07.

## This repository

A flagship project of the [Hidden Alchemy](https://github.com/Hidden-Alchemy)
laboratory — the org pipeline (`IDEA → CONCEPT → ARCHITECTURE → SYSTEM →
AUTOMATION → REALITY`) made concrete end-to-end. The org builds, runs, and
demonstrates the very workflow this tool automates.

> - **Pipeline stage:** currently CONCEPT — it has passed Research (go/no-go
>   recorded in [ideas#3](https://github.com/Hidden-Alchemy/ideas/issues/3))
>   and is awaiting its Architecture note (project board: [Idea Lifecycle](https://github.com/orgs/Hidden-Alchemy/projects/1)).

The work today is honest and small: a project repository, a written
architecture, and an evaluation harness — not a mocked-up demo. The repository
name and identity are fixed; the scope below is the working contract.

## What this is / is not

**This is:**
- A **CLI-first** staged pipeline: each org stage produces a concrete artifact
  (spec draft, feasibility note, architecture sketch, scaffolded project).
- An offline **evaluation harness** that scores generated artifacts for
  quality, so the tool's output is graded with receipts, not vibes.
- **Provider-agnostic** prompt and template files — no hard dependency on any
  single model vendor.
- A public, auditable paper trail: every artifact it produces is a text file
  the tool leaves for a human to inspect.

**This is NOT:**
- A **GUI-first** product in v0. If a web UI arrives it is after the CLI
  proves the pipeline — not before.
- An **auto-shipping code generator** that deploys without a human. Every
  go/no-go decision in the pipeline stays human (org rule §21).
- A way to replace maintainers, a chatbot wrapper course, or a storehouse for
  API keys and org secrets (no secrets live in this repository).

## Architecture

Four layers, each one artifact-shaped:

1. **Stages** (`idea.md → concept.md → architecture.md → system/`) — a
   directory walk where each stage reads the previous artifact and emits the
   next via a prompt chain.
2. **Templates** (`templates/*.jinja`, `templates/*.md`) — spec and feasibility
   skeletons matching the org's own §15 design system.
3. **Eval harness** (`eval/`) — offline scoring of generated artifacts against
   rubrics; raw outputs published, never hidden.
4. **Human gate** — a review step between every stage transition; nothing moves
   forward without a recorded decision (mirrors §23's go/no-go).

The prompt chain is the core product; the eval harness is what keeps it honest.

## Installation / Quick Start

No runnable software exists yet (status: `concept`). The first command a user
will run once v0 ships is:

```sh
idea-forge scaffold ./my-idea.md   # emits ./stages/concept.md + feasibility note
```

Until then, "how it works" is documented above and tracked on the project
board; nothing here pretends to be installable.

## How to contribute

Follow the org-wide [CONTRIBUTING.md](https://github.com/Hidden-Alchemy/.github/blob/main/CONTRIBUTING.md).
Small documentation fixes need no pre-approval; code changes start by
commenting intent on a `good first issue` or opening a draft PR. Strong
first-contribution surfaces now:

- **Eval-harness fixtures** — sample idea→concept pairs with hand-scored
  labels for grading tests.
- **Template drafts** — spec/feasibility skeletons written against the org's
  §15 design system.
- **Prompt-engineering evals** — grading chains against the rubric.

Live work is tracked on the [Idea Lifecycle board](https://github.com/orgs/Hidden-Alchemy/projects/1)
and the originating [idea issue](https://github.com/Hidden-Alchemy/ideas/issues/3).

## Roadmap

- Research complete (GO recorded) — held in ideas#3.
- **Next:** Architecture note for v0 (CLI, staged artifacts, eval harness).
- **Then:** v0 CLI + template set; eval-harness fixtures with human-scored labels.
- **Then:** Prototype status, evaluated against the rubric before anything is
  called `active`.
  No dates are promised; progress is visible on the board, honestly.

## Maintainers

- [@Hassan0703](https://github.com/Hassan0703) — primary accountable maintainer

## License

MIT — see [LICENSE](LICENSE). Back to the [organization profile](https://github.com/Hidden-Alchemy).