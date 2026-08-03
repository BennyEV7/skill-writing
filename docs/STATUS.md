# Status — skill-writing

**Last updated:** 2026-08-02  
**Phase:** 3 — Smoke-check (Grok T1–T5 supervised pass recorded)

## Current state (plain English)

Two writing skills live under `skills/` with composition rules, private-use docs, and a trigger-test matrix. Grok completed a supervised T1–T5 run (chat-only drafts + results log). That run does not fully prove cold-start auto-invocation. The automated installer remains removed; installs stay human-only.

## What exists

| Area | State |
| --- | --- |
| Docs / agent rules | Customized; Codex remediation applied |
| `skills/writing-simplified-technical-english` | Present |
| `skills/writing-clarity-and-grace` | Present |
| Installer | **Removed** (by design) |
| `setup-project-files.md` | **Removed** |
| `docs/TRIGGER-TESTS.md` | Present (includes skill self-report) |
| `docs/test-results/` | Present; `2026-08-02_grok_T1-T5.md` recorded |
| Git | Initialized as part of hardening |

## What’s working

- Two-skill split with when/when-not and small-edit rules
- Domain vs writing composition documented
- No automated overwrite risk from this repo

## What’s blocked / unknown

- Cold-start auto-invocation (fresh session, no matrix priming) not yet measured
- Claude Code / Codex T1–T5 not run

## Next 1–3 steps

1. Optional: re-run T1–T2 in a fresh Grok session without naming skills
2. Run T1–T5 on Claude Code and/or Codex; log under `docs/test-results/`
3. Tighten skill descriptions only if cold-start or other agents fail

## Session log (newest first)

### 2026-08-02 — Grok T1–T5 supervised run

- Executed T1–T5 chat-only with skill self-report
- Logged `docs/test-results/2026-08-02_grok_T1-T5.md` — all pass (auto-invoke caveat noted)

### 2026-08-02 — Trigger test logging

- Required skill self-report (“which skill and why”) on every trigger case
- Added `docs/test-results/` with README and `_template.md`

### 2026-08-02 — Codex remediation

- Removed `scripts/install-skills.ps1` (prefer no installer over risky overwrite)
- Removed `setup-project-files.md` (obsolete template guide)
- Added composition rules to both skills + AGENTS.md
- README: private use; manual skill linking only
- Added `docs/TRIGGER-TESTS.md` with acceptance criteria
- Git init / initial commit for history

### 2026-08-02 — Foundation + skills + install (earlier)

- Authored both skills; temporary installer created junctions (later removed from repo)
