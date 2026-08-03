# Test results

Store **trigger-test run logs** here. The matrix and rubrics live in [../TRIGGER-TESTS.md](../TRIGGER-TESTS.md).

## How to add a run

1. Copy `_template.md` to a new file:

   `YYYY-MM-DD_<agent>_T1-T5.md`

   Examples: `2026-08-02_grok_T1-T5.md`, `2026-08-03_claude_T1-T8.md`

2. Fill each case: result, skill self-report (quoted), prose notes, pass/fail.

3. Optionally paste a short excerpt of the agent output (not the whole chat).

4. Update `docs/STATUS.md` when Phase 3 criteria change (e.g. T1–T5 first pass).

## Naming

| Part | Values |
| --- | --- |
| Date | ISO `YYYY-MM-DD` |
| Agent | `grok`, `claude`, `codex`, or other short id |
| Scope | `T1-T5`, `T1-T8`, `T3-retry`, etc. |

## Safety

Prefer chat-only test prompts. Result files are the intended disk writes after a run (created by you or when you ask the agent to log results).
