# Status — skill-writing

**Last updated:** 2026-08-04
**Phase:** 3 — Short-form smoke-check complete; long-form T9 ready for multi-agent runs

## Current state (plain English)

Two writing skills live under `skills/`. The clarity-and-grace skill now
includes genre-specific long-form guidance, cadence checks, and a
multi-paragraph example. T9 provides a neutral 700–900 word article test for
Codex, Claude, and Grok. Existing short-form tests passed across all three
agents; multi-agent T5 and T9 runs remain open.

## What exists

| Area | State |
| --- | --- |
| Docs / agent rules | Aligned with `testing/` + current skill scope |
| `skills/writing-simplified-technical-english` | Present; hard rules + cheatsheet expanded |
| `skills/writing-clarity-and-grace` | Present; explicit long-form flow, paragraph, cadence, and anti-pattern guidance |
| `chatgpt-custom-instructions.md` | Paste pack synchronized with long-form guidance |
| Installer | **Removed** (by design) |
| `testing/` | Neutral fixtures, two-turn cold protocol, T9 long-form test, multi-agent scores |
| Git | Remote `origin` (private GitHub) |

## What’s working

- Two-skill split with when/when-not, composition, and small-edit rules
- Neutral fixtures + cold auto-invoke measured (T1/T2 ×3 agents)
- Richer Style and STE guidance for harder revision moves
- Long-form rules counter presentation-slide prose without flattening short formats
- ChatGPT path without skill routing (single instruction block)

## What’s blocked / unknown

- Multi-agent **T5** (small-edit) not re-run after testing/ move and rule expansions
- Multi-agent **T9** long-form outputs not run or scored yet
- Whether expanded rules need a light cold re-smoke (optional; not required unless quality drops)
- Independent `Score-Codex.md` may differ slightly from `SCORED.md` on a few cells

## Next 1–3 steps

1. Run multi-agent T9; preserve and score each raw article
2. Run multi-agent T5; log under `testing/test-results/`
3. Adjust the skill only if the new evidence exposes another gap

## Session log (newest first)

### 2026-08-04 — Long-form cadence hardening

- Replaced blanket short-paragraph guidance with genre-sensitive development.
- Added outline-to-argument rules and warnings for slide prose, fragment chains, repeated thesis statements, and slogan saturation.
- Added a multi-paragraph example and synchronized the ChatGPT paste pack.
- Added neutral T9 fixture, prompt, rubric, and result fields; model runs remain pending.

### 2026-08-03 — Skill rule expansions + ChatGPT pack (other agent)

- Style: passive-OK nuance, cohesion naming, cleft/modifier emphasis, longer-shape, fidelity/honesty, elegance, correctness vs folklore; cheatsheet + examples extended
- STE: ~20/25 word caps, noun-stack cap, tense control, no bare telegrams, short paragraphs; cheatsheet aligned
- Added `chatgpt-custom-instructions.md` (merged technical + people-facing registers for ChatGPT custom instructions)
- Prior partial commit on remote: `f1226e1` (“update rules and examples”)

### 2026-08-03 — Admin close-out + multi-agent scores on git

- `testing/` layout, fixtures, `2026-08-03-001/SCORED.md` on `master`
- D-011 neutral fixtures; cold Phase 3 gate met

### 2026-08-03 — Multi-agent scoring batch

- Cold T1+T2 strong pass ×3; T3–T4, T6–T8 pass ×3 after Codex fixes/retest
- T5 not in batch

### 2026-08-02 — Foundation + hardening

- Both skills authored; installer removed; private use; composition rules
