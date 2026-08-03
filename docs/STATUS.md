# Status — skill-writing

**Last updated:** 2026-08-03  
**Phase:** 3 — Smoke-check (cold auto-invoke met; multi-agent T5 still open)

## Current state (plain English)

Two writing skills live under `skills/`. Trigger tests, neutral fixtures, and scored results live under `testing/`. Multi-agent batch `testing/test-results/2026-08-03-001/` (see `SCORED.md`): **cold T1 + T2 strong pass** and **T3–T4, T6–T8 pass** on Grok, Claude, and Codex. **T5** was not in that batch (earlier supervised Grok pass only). Installer remains removed by design.

## What exists

| Area | State |
| --- | --- |
| Docs / agent rules | Customized; aligned with `testing/` layout |
| `skills/writing-simplified-technical-english` | Present |
| `skills/writing-clarity-and-grace` | Present |
| Installer | **Removed** (by design) |
| `testing/TRIGGER-TESTS.md` | Two-turn cold protocol, rubrics, fixture paths |
| `testing/testing-files/` | Neutral Northline Inventory fixtures T1–T8 |
| `testing/test-results/` | Supervised Grok T1–T5 + multi-agent `2026-08-03-001/` |
| Git | Remote `origin` (private GitHub) |

## What’s working

- Two-skill split with when/when-not and small-edit rules
- Domain vs writing composition documented
- Neutral fixtures + two-turn cold protocol
- **Cold auto-invoke T1 (STE) and T2 (Style)** on Grok, Claude, Codex
- Overrides (T3–T4) and optional cases (T6–T8) pass on all three agents in `SCORED.md`

## What’s blocked / unknown

- Multi-agent **T5** (small-edit only) not re-run after the testing/ move
- Independent scorer note: `2026-08-03-001/Score-Codex.md` may differ slightly from `SCORED.md` on a few cells; treat `SCORED.md` as the operator-maintained summary

## Next 1–3 steps

1. Run T5 on Grok, Claude, and Codex; log under `testing/test-results/`
2. Tighten skill descriptions only if T5 or a future cold retest fails
3. Optional: expand example banks (Phase 4)

## Session log (newest first)

### 2026-08-03 — Admin close-out + multi-agent scores on git

- Finalized STATUS/PLAN/CHARTER/AGENTS for post-score state
- Committed `testing/` layout, fixtures, transcripts, and `SCORED.md`

### 2026-08-03 — Rescore Codex T8 retest

- `t8-Codex`: Style skill + benefit-led blurb → **pass**
- T6–T8 complete for all three agents in `SCORED.md`

### 2026-08-03 — Rescore Codex T4/T6/T7 after log fixes

- T4 Style override, T6 justified STE default, T7 facts+Style → pass

### 2026-08-03 — Score multi-agent run 2026-08-03-001

- Cold T1+T2 **pass (strong)** ×3 agents; Phase 3 cold gate **met**
- Detail: `testing/test-results/2026-08-03-001/SCORED.md`

### 2026-08-03 — testing/ layout + neutral fixtures

- Moved trigger tests from `docs/` to `testing/`
- Added `testing/testing-files/` (Northline Inventory; not writing-skills meta)
- D-011 recorded

### 2026-08-03 — Two-turn cold-start protocol

- Self-report is turn 2 only for cold T1/T2

### 2026-08-02 — Grok T1–T5 supervised run

- Logged at `testing/test-results/2026-08-02_grok_T1-T5.md` (supervised; auto-invoke caveat)

### 2026-08-02 — Codex remediation + foundation

- No installer; private use; composition rules; skills authored
