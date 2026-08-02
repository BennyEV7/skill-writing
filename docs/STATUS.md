# Status — skill-writing

**Last updated:** 2026-08-02  
**Phase:** 3 — Smoke-check (matrix ready; live runs pending)

## Current state (plain English)

Two writing skills live under `skills/` with composition rules, private-use docs, and a trigger-test matrix. The automated installer was **removed** after risk review. Agent skill homes (if already junctioned) still work; further installs are human-only. Git history is being established for rollback.

## What exists

| Area | State |
| --- | --- |
| Docs / agent rules | Customized; Codex remediation applied |
| `skills/writing-simplified-technical-english` | Present |
| `skills/writing-clarity-and-grace` | Present |
| Installer | **Removed** (by design) |
| `setup-project-files.md` | **Removed** |
| `docs/TRIGGER-TESTS.md` | Present |
| Git | Initialized as part of hardening |

## What’s working

- Two-skill split with when/when-not and small-edit rules
- Domain vs writing composition documented
- No automated overwrite risk from this repo

## What’s blocked / unknown

- Live T1–T5 results not yet recorded for any agent

## Next 1–3 steps

1. Run trigger tests T1–T5 on Grok
2. Log pass/fail in `docs/TRIGGER-TESTS.md`
3. Tighten descriptions only if tests fail

## Session log (newest first)

### 2026-08-02 — Codex remediation

- Removed `scripts/install-skills.ps1` (prefer no installer over risky overwrite)
- Removed `setup-project-files.md` (obsolete template guide)
- Added composition rules to both skills + AGENTS.md
- README: private use; manual skill linking only
- Added `docs/TRIGGER-TESTS.md` with acceptance criteria
- Git init / initial commit for history

### 2026-08-02 — Foundation + skills + install (earlier)

- Authored both skills; temporary installer created junctions (later removed from repo)
