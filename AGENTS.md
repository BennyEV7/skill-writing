# AGENTS.md — shared project brain

This file is the **single source of truth** for AI coding agents working in this repository.

Tool-specific files (e.g. `CLAUDE.md`) should only point here — do not maintain a second full rulebook.

## Before substantial work

1. Read this file.
2. Read [docs/STATUS.md](docs/STATUS.md).
3. Read [docs/PLAN.md](docs/PLAN.md).
4. Skim [docs/CHARTER.md](docs/CHARTER.md) if the task touches goals or scope.
5. Check [docs/DECISIONS.md](docs/DECISIONS.md) before reversing an existing choice.

## What this project is

**skill-writing** — Author and maintain global writing skills for AI agents (Grok, Claude Code, Codex).

- **Is:** Canonical source for agent writing skills: STE-inspired technical prose and Style/clarity external prose.
- **Is:** Docs and a trigger-test harness under `testing/` so the same skills can be checked across agents.
- **Is not:** A full ASD-STE100 compliance product or a reproduction of copyrighted style manuals.
- **Is not:** An automated installer (skills reach agent homes only by human junction/copy).
- **Constraint:** Skills must stay lean, portable (`SKILL.md` standard), and legally careful (inspired/distilled content only).

## Audience and tone

- Prefer plain language suitable for non-specialists and future collaborators.
- Explain tradeoffs briefly when asking the human to choose.
- Prefer simple, working foundations over clever architecture.
- When editing skill bodies, optimize for **agent actionability** (when/when-not, checklists, examples), not essay form.

## Writing style in this repo

- Use the **writing-simplified-technical-english** skill for in-repo docs, skill instructions that describe procedures, commit/PR prose, and product/help-style content.
- Use the **writing-clarity-and-grace** skill for external-facing drafts (emails, posts, marketing) if you write those here.
- Priority: explicit user request > this file > writing skills.
- **Composition:** domain skills own workflow and facts; writing skills own prose quality only. Do not let a writing skill override another skill’s required structure.
- Trigger tests live under `testing/` (see `testing/TRIGGER-TESTS.md`). Fixtures in `testing/testing-files/` are neutral (fictional product); do not replace them with text about writing skills when running cold-start tests.

## Project memory

| File | Agents should… |
| --- | --- |
| `docs/STATUS.md` | Update after meaningful sessions |
| `docs/PLAN.md` | Update when phases or priorities change |
| `docs/DECISIONS.md` | Append when a lasting choice is made |
| `docs/CHARTER.md` | Change only when goals/scope truly change |
| `AGENTS.md` | Keep concise; prune rather than endlessly append |

## Working agreements

- Prefer small, reversible steps; confirm before destructive or hard-to-undo actions.
- Do not invent credentials, secrets, or unverified metrics.
- When product direction is unclear, ask with clear options instead of silently guessing.
- Match existing skill and docs style once they exist.
- Canonical skill source is `skills/`. Do **not** add an install script that overwrites agent skill directories. Edit only this repo; agent homes should link or copy skills only when the human does it deliberately.

## Session close-out

When a session made lasting changes:

1. Update `docs/STATUS.md`
2. Append `docs/DECISIONS.md` if a real decision was made
3. Adjust `docs/PLAN.md` if the roadmap shifted

## Out of scope (for now)

- Full ASD-STE100 dictionary or certified compliance tooling
- Reproducing *Style: Ten Lessons in Clarity and Grace* lesson text
- Automatic CI linters for prose
- Per-client brand voice packs
- Non-English STE variants
- Automated installers that write under agent skill homes
- Public redistribution packaging

## Maintaining this file

Keep entries short and project-intrinsic. Link to authoritative docs or code instead of duplicating them.
