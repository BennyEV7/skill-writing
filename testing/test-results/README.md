# Test results

Store **trigger-test run logs** here. Protocols and prompts: [../TRIGGER-TESTS.md](../TRIGGER-TESTS.md).  
Fixtures: [../testing-files/](../testing-files/).

## How to add a run

1. Copy `_template.md` to:

   `YYYY-MM-DD_<agent>_<scope>.md`

   Examples: `2026-08-03_grok_T1-cold.md`, `2026-08-03_claude_T1-T5-same-thread.md`

   Or keep raw transcripts in a dated folder (e.g. `2026-08-03-001/`) and add a `SCORED.md` after scoring.

2. Fill mode (cold / warm / supervised), turn-1 UI skill load, turn-1 prose, turn-2 self-report, pass/fail.

3. Optionally paste a short draft excerpt.

4. Update `docs/STATUS.md` when Phase 3 status changes.

## Scored multi-agent batch

| Folder | Notes |
| --- | --- |
| [2026-08-03-001/SCORED.md](2026-08-03-001/SCORED.md) | Cold T1–T2 strong ×3 agents; T3–T8 partial; see data-quality notes |

## Naming

| Part | Values |
| --- | --- |
| Date | ISO `YYYY-MM-DD` |
| Agent | `grok`, `claude`, `codex`, … |
| Scope | `T1-cold`, `T2-cold`, `T1-T5-same-thread`, `T3-T5-warm`, … |

Label **cold** only for two-turn, task-only turn 1 in a fresh session, using neutral fixtures (not writing-skill-themed text).

## Staging from another project

Copy logs from e.g. `skills-testing/results/` into this folder, then score against [../TRIGGER-TESTS.md](../TRIGGER-TESTS.md).
