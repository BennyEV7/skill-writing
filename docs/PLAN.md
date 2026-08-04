# Plan — skill-writing

**Last updated:** 2026-08-04
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
- [x] Rule/example expansion pass (tense/paragraph/word caps; Style elegance, fidelity, emphasis devices, folklore table)

### Phase 2 — Multi-agent availability (manual)

- [x] Skills authored under `skills/` as canonical source
- [x] **No automated installer** (removed after risk review)
- [x] Document manual junction/copy only; human-supervised
- [x] Composition rules: domain skills vs writing skills
- [x] Optional ChatGPT paste pack (`chatgpt-custom-instructions.md`)

### Phase 2.5 — Hardening (Codex review)

- [x] Remove unsafe installer rather than “fix and keep”
- [x] Remove obsolete `setup-project-files.md`
- [x] Private-use / no-redistribution clarity in README
- [x] Git repository for history and rollback
- [x] Trigger-test matrix + measurable acceptance criteria

### Phase 3 — Smoke-check

- [x] Matrix and acceptance criteria in `testing/TRIGGER-TESTS.md`
- [x] Two-turn cold-start protocol; results in `testing/test-results/`
- [x] Neutral fixtures in `testing/testing-files/` (not writing-skill-themed)
- [x] T1–T5 pass on at least one agent (Grok supervised: `2026-08-02_grok_T1-T5.md`)
- [x] Cold-start T1 + T2 (two-turn) on ≥1 agent — Grok, Claude, Codex strong pass (`2026-08-03-001/SCORED.md`)
- [x] Multi-agent rows for T1–T4 and T6–T8 (pass ×3 in `SCORED.md`)
- [ ] Multi-agent **T5** (small-edit) re-run after testing/ move and rule expansions
- [x] T9 neutral long-form fixture, prompt, and rubric
- [ ] Multi-agent **T9** long-form run on Codex, Claude, and Grok

### Phase 4 — Later / optional

- [ ] More example banks (partially started in Style references)
- [ ] `agents/openai.yaml` for Codex UI polish
- [ ] Formal open license (only if publishing)
- [ ] Cross-platform install notes (still manual)
- [ ] User-supplied STE dictionary hook if licensed materials appear
- [ ] Optional cold spot-check after major skill edits

## Near-term next actions

1. Run T9 on Grok, Claude, and Codex; preserve and score the raw outputs.
2. Run T5 on Grok, Claude, and Codex; store transcripts and update scores.
3. Adjust skill guidance only if those runs expose a real miss.

## Explicitly later / maybe never

- Automated skill installers
- Certified ASD-STE100 tooling
- CI prose linters
- Per-client brand packs
- Public distribution

## How to update this plan

- Mark checkboxes when done.
- Keep phases coarse; put session detail in `STATUS.md`.
