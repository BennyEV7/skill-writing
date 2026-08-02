# Trigger tests — writing skills

**Purpose:** Measure whether agents pick the right writing skill and follow small-edit / override rules.  
**Last updated:** 2026-08-02

Skills under test:

- `writing-simplified-technical-english` (STE)
- `writing-clarity-and-grace` (Style)

## Phase 3 acceptance criteria

Phase 3 **passes** when:

1. Cases **T1–T5** pass on at least **one** agent (Grok preferred for first pass).
2. Results are recorded in the results table below (agent, date, pass/fail, notes).
3. Failures either get a skill-description / when-not fix, or an explicit “accepted limitation” note in `docs/STATUS.md`.

Optional stretch: T6–T8 and Claude/Codex rows.

## How to run a case

1. Start a fresh-enough session (or reload skills if the agent supports it).
2. Use the prompt in the matrix (adapt paths only if needed).
3. Judge against **Acceptance signal** (not perfect prose — routing and constraints).
4. Record pass/fail and a one-line note.

Do **not** use an installer for these tests. Skills must already be discoverable.

## Matrix

| ID | Prompt / situation | Expected skill | Acceptance signal |
| --- | --- | --- | --- |
| T1 | In this repo: “Rewrite the Getting started section of the README in clear technical English.” | STE | Short active sentences; consistent terms; no marketing voice |
| T2 | “Draft a customer email: we delay launch by one week; billing edge case; new date next Friday.” | Style | Actor/action; point early; clear next step/ask |
| T3 | “Rewrite this email in STE” (paste a soft email draft) | STE (override) | Explicit override wins; more procedural/plain than Style |
| T4 | “Rewrite this README blurb with Style clarity-and-grace principles” (paste a dry blurb) | Style (override) | Explicit override wins; flow/emphasis without full STE flatness |
| T5 | Open a long doc; “Fix **only** this one sentence: …” | Active skill + **small-edit** | Only the requested span changes; no full-file rewrite |
| T6 | “Make this clearer” on mixed technical + stakeholder text with no audience stated | Ask **or** default by context | No silent full style swap that fights obvious audience |
| T7 | Domain task + “write the summary clearly” (e.g. spreadsheet or SEO skill if present) | Domain workflow + writing polish | Domain steps/structure preserved; prose improved |
| T8 | “Write a short landing-page blurb for a status-update tool.” | Style, not STE | Persuasion/CTA allowed; not robotic STE procedure tone |

## Pass/fail rubrics (detail)

### T1 (STE positive)

- **Pass:** Prefer active voice; concrete verbs; limited synonym churn; protected tokens unchanged if present.
- **Fail:** Long throat-clearing; marketing hype; external email tone.

### T2 (Style positive)

- **Pass:** Real actors as subjects; main point early; readable paragraphs; clear close.
- **Fail:** STE-only telegram style with no audience shape; buried decision; empty openers kept.

### T3 / T4 (overrides)

- **Pass:** Stated skill/style clearly followed despite default context.
- **Fail:** Agent ignores the override and uses the other writing mode.

### T5 (small-edit)

- **Pass:** Diff limited to the requested sentence (plus at most a trivial neighbor fix for grammar).
- **Fail:** Whole section or file restyled.

### T6 (ambiguous)

- **Pass:** One clarifying question, **or** a justified default with a short note of the assumption.
- **Fail:** Confident wrong full rewrite with no signal.

### T7 (composition)

- **Pass:** Domain skill constraints/templates kept; wording improved.
- **Fail:** Writing skill replaces domain workflow or required structure.

### T8 (Style marketing)

- **Pass:** Benefit-led, concise, non-jargon; may use light emphasis.
- **Fail:** Operator-manual STE; empty superlatives only.

## Results log

Record newest runs at the top of each agent section.

### Grok

| ID | Date | Result | Notes |
| --- | --- | --- | --- |
| T1–T8 | — | Not run | Matrix authored; live pass pending |

### Claude Code

| ID | Date | Result | Notes |
| --- | --- | --- | --- |
| T1–T8 | — | Not run | |

### Codex

| ID | Date | Result | Notes |
| --- | --- | --- | --- |
| T1–T8 | — | Not run | |

## After failures

1. Adjust skill `description` trigger phrases and when/when-not sections.
2. Re-run the failed IDs only.
3. Note the change in `docs/STATUS.md` session log.
