# Plan — skill-writing

**Last updated:** 2026-08-02  
**Horizon:** Safe personal use of global writing skills (no automated installer)

## North star

Agents reliably use STE-inspired rules for in-project technical writing and Style/clarity principles for external communication, from one maintained source under Git.

## Phases

### Phase 0 — Foundation

- [x] Charter, plan, status, decisions filled in
- [x] Shared agent brain (`AGENTS.md`) in place
- [x] README usable by a newcomer

### Phase 1 — Author skills

- [x] `skills/writing-simplified-technical-english/` (SKILL.md + references)
- [x] `skills/writing-clarity-and-grace/` (SKILL.md + references)
- [x] Sharp descriptions and when/when-not rules

### Phase 2 — Multi-agent availability (manual)

- [x] Skills authored under `skills/` as canonical source
- [x] **No automated installer** (removed after risk review)
- [x] Document manual junction/copy only; human-supervised
- [x] Composition rules: domain skills vs writing skills

### Phase 2.5 — Hardening (Codex review)

- [x] Remove unsafe installer rather than “fix and keep”
- [x] Remove obsolete `setup-project-files.md`
- [x] Private-use / no-redistribution clarity in README
- [x] Git repository for history and rollback
- [x] Trigger-test matrix + measurable acceptance criteria

### Phase 3 — Smoke-check

- [x] Matrix and acceptance criteria in `docs/TRIGGER-TESTS.md`
- [x] Skill self-report required on every case; results folder `docs/test-results/`
- [x] T1–T5 pass on at least one agent (Grok supervised run: `docs/test-results/2026-08-02_grok_T1-T5.md`)
- [ ] Optional: cold-start auto-invoke check (fresh session, no matrix priming)
- [ ] Optional: Claude / Codex rows
- [ ] Optional: T6–T8

### Phase 4 — Later / optional

- [ ] More example banks
- [ ] `agents/openai.yaml` for Codex UI polish
- [ ] Formal open license (only if publishing)
- [ ] Cross-platform install notes (still manual)
- [ ] User-supplied STE dictionary hook if licensed materials appear

## Near-term next actions

1. Run T1–T5 on Grok; log results in `docs/TRIGGER-TESTS.md`.
2. Adjust skill descriptions if auto-invocation misses.
3. Commit after each meaningful skill edit.

## Explicitly later / maybe never

- Automated skill installers
- Certified ASD-STE100 tooling
- CI prose linters
- Per-client brand packs
- Public distribution

## How to update this plan

- Mark checkboxes when done.
- Keep phases coarse; put session detail in `STATUS.md`.
