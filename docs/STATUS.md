# Status — skill-writing

**Last updated:** 2026-08-03  
**Phase:** 3 — Smoke-check complete for cold auto-invoke; skill rules expanded; multi-agent T5 still open

## Current state (plain English)

Two writing skills live under `skills/` with **expanded rules and examples** (Style: elegance, fidelity, emphasis devices, correctness vs folklore; STE: word/tense/paragraph caps). Trigger tests and scored multi-agent results live under `testing/`. Cold T1–T2 and T3–T4/T6–T8 passed on Grok, Claude, and Codex (`2026-08-03-001/SCORED.md`). **T5** multi-agent re-run still open. Optional **ChatGPT** one-block custom instructions live at repo root (`chatgpt-custom-instructions.md`). Installer remains removed.

## What exists

| Area | State |
| --- | --- |
| Docs / agent rules | Aligned with `testing/` + current skill scope |
| `skills/writing-simplified-technical-english` | Present; hard rules + cheatsheet expanded |
| `skills/writing-clarity-and-grace` | Present; principles 9–11 + cheatsheet/examples expanded |
| `chatgpt-custom-instructions.md` | Paste pack for ChatGPT (merged registers) |
| Installer | **Removed** (by design) |
| `testing/` | Neutral fixtures, two-turn cold protocol, multi-agent scores |
| Git | Remote `origin` (private GitHub) |

## What’s working

- Two-skill split with when/when-not, composition, and small-edit rules
- Neutral fixtures + cold auto-invoke measured (T1/T2 ×3 agents)
- Richer Style and STE guidance for harder revision moves
- ChatGPT path without skill routing (single instruction block)

## What’s blocked / unknown

- Multi-agent **T5** (small-edit) not re-run after testing/ move and rule expansions
- Whether expanded rules need a light cold re-smoke (optional; not required unless quality drops)
- Independent `Score-Codex.md` may differ slightly from `SCORED.md` on a few cells

## Next 1–3 steps

1. Run multi-agent T5; log under `testing/test-results/`
2. Optional: quick cold T1/T2 spot-check after rule expansions if agents misbehave
3. Phase 4 only if personal use shows a gap (more examples, formal license, etc.)

## Session log (newest first)

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
