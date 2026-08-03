# Decisions — skill-writing

Record **lasting** choices here so future humans and agents don’t re-debate them.

Format: newest first. Keep each entry short. To reverse a decision, add a new entry that supersedes the old one.

---

## D-011 — Neutral test fixtures under `testing/`

- **Date:** 2026-08-03
- **Status:** Accepted
- **Decision:** Trigger tests, results, and fixtures live under `testing/`. Fixture text uses a fictional warehouse product (Northline Inventory), not writing-skills content. Cold-start prompts must not prime agents with meta text about skills or this harness.
- **Why:** Skill-themed fixtures can hide cold-start routing failures.
- **Consequences:** Do not use this repo’s real README as the T1 cold-start source. Prefer `testing/testing-files/`.

---

## D-010 — No automated installer

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** Remove `scripts/install-skills.ps1` and do not ship an installer. Skill availability in agent homes is **human-supervised** (manual junction or copy only).
- **Why:** An installer that replaces skill directories can destroy local customizations. Hardening was less valuable than eliminating the hazard for personal use.
- **Consequences:** README documents manual linking only. Agents must not add a destructive install script without a new decision.
- **Supersedes:** D-002’s “install via script” mechanism (canonical source under `skills/` remains).

---

## D-009 — Private use; no open license for now

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** This is a private personal project. No formal open-source LICENSE. Not licensed for redistribution or contribution.
- **Why:** Distribution readiness is out of scope; ambiguous “personal use” without a clear no-redistribution stance was a review finding.
- **Consequences:** README states private use. Add a real license only if publishing later.

---

## D-008 — Domain skills vs writing skills composition

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** Domain skills own facts, workflow, tools, and structure. Writing skills own prose quality only. Writing skills must not override domain templates or steps.
- **Why:** Broad writing triggers can collide with specialized skills (SEO, support, spreadsheets, etc.).
- **Consequences:** Both `SKILL.md` files and `AGENTS.md` state the composition rule.

---

## D-007 — Git is the rollback story

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** Keep this project as a Git worktree; commit meaningful skill and docs changes. Prefer commits before risky skill edits when agent homes junction to this tree.
- **Why:** Without history, live junctions make mistakes immediate and hard to reverse.
- **Consequences:** Agents should treat uncommitted skill edits as high impact if junctions exist.

---

## D-006 — Skill names: long form + `writing-` prefix

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** Skills are named `writing-simplified-technical-english` and `writing-clarity-and-grace` (not short forms like `ste-writing` / `style-clarity`).
- **Why:** Clearer discovery and grouping under a shared `writing-` namespace.
- **Consequences:** Directory names and slash commands use these full names.

---

## D-005 — STE-inspired, not full ASD-STE100 compliance

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** The technical skill teaches STE-inspired principles without claiming certified ASD-STE100 compliance and without shipping a proprietary controlled dictionary.
- **Why:** Full STE requires licensed materials; principles deliver most agent benefit with lower legal and maintenance cost.
- **Consequences:** Skill and docs must say “inspired by” / “principles,” never “compliant with ASD-STE100.”

---

## D-004 — Style skill is distilled principles, not book text

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** The external-writing skill encodes original agent checklists based on clarity principles popularized by *Style: Ten Lessons in Clarity and Grace* (Williams/Bizup). It does not reproduce lesson text from the book.
- **Why:** Copyright and maintainability.
- **Consequences:** No long quotations or chapter dumps; teach diagnose → revise behaviors.

---

## D-003 — Two skills, auto by context

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** Separate skills for in-project technical prose (STE-inspired) and external communication (Style/clarity). Auto-select via skill descriptions and triggers; explicit user request always wins.
- **Why:** Auto-invocation works better with distinct intents than one mega-skill with modes.
- **Consequences:** Maintain clear when/when-not sections in both skills.

---

## D-002 — Canonical source in this repo

- **Date:** 2026-08-02
- **Status:** Accepted (mechanism updated by D-010)
- **Decision:** Canonical skill trees live in this repo under `skills/`. Agent homes may link or copy those trees only under human control.
- **Why:** One source of truth for Grok, Claude Code, and Codex.
- **Consequences:** Edit only the repo copy. Automated install scripts are out of scope (see D-010).

---

## D-001 — Docs layout: `docs/` + root agent files

- **Date:** 2026-08-02
- **Status:** Accepted
- **Decision:** Human project memory lives under `docs/`. Shared agent brain is root `AGENTS.md`. Tool-specific files are thin pointers only.
- **Why:** One brain avoids multi-agent drift; small docs set stays maintainable.
- **Consequences:** Update `AGENTS.md` for agent behavior; update `docs/*` for product/project memory.

---

## Open decisions (not yet accepted)

| ID | Question | Options / notes |
| --- | --- | --- |
| — | None currently | — |

When you settle one, promote it to a full `D-00x` entry above and remove it from this table.
