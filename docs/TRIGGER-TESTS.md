# Trigger tests — writing skills

**Purpose:** Measure whether agents pick the right writing skill and follow small-edit / override rules.  
**Last updated:** 2026-08-02

Skills under test:

- `writing-simplified-technical-english` (STE)
- `writing-clarity-and-grace` (Style)

**Results folder:** [test-results/](test-results/) — one file (or section) per run. Do not leave results only in chat.

## Phase 3 acceptance criteria

Phase 3 **passes** when:

1. Cases **T1–T5** pass on at least **one** agent (Grok preferred for first pass).
2. Results are recorded under `docs/test-results/` (see template there).
3. Failures either get a skill-description / when-not fix, or an explicit “accepted limitation” note in `docs/STATUS.md`.

Optional stretch: T6–T8 and Claude/Codex rows.

## How to run a case

1. Start a fresh-enough session (or reload skills if the agent supports it).
2. Prefer **chat-only** prompts (no file writes) unless you intentionally use a scratch file for T5.
3. Use the prompt in the matrix, and **always** append the skill self-report block (below).
4. Judge against **Acceptance signal** (not perfect prose — routing and constraints).
5. Save the result under `docs/test-results/` using the template.

Do **not** use an installer for these tests. Skills must already be discoverable.

### Required: skill self-report

Every test prompt must end with:

```text
After your draft, state:
1. Which writing skill you applied (full name), or "none" if you did not use a writing skill.
2. Why you chose that skill (one or two sentences).
3. Whether any other skill also applied (domain or otherwise).

Show the result in chat only. Do not create, edit, or delete any files unless I explicitly ask you to log results.
```

**Why:** Self-report makes routing failures obvious (wrong skill claimed, no skill loaded, or skill claimed but prose does not match).

**Scoring the self-report:**

| Observation | How to score |
| --- | --- |
| Correct skill name + reason matches expected row | Routing **pass** (still check prose rubric) |
| Wrong skill name, or “none” when a writing skill was expected | Routing **fail** |
| Correct name but prose clearly follows the other style | Routing **fail** (claim/behavior mismatch) |
| Domain skill + writing skill both named appropriately (T7) | Composition **pass** if structure preserved |

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

Always append the **skill self-report** block to the prompt for every ID.

## Ready-to-paste prompt shells

### T1 (STE, chat-only)

```text
Rewrite the Getting started section of this repo’s README in clear technical English.
After your draft, state:
1. Which writing skill you applied (full name), or "none" if you did not use a writing skill.
2. Why you chose that skill (one or two sentences).
3. Whether any other skill also applied (domain or otherwise).

Show the result in chat only. Do not create, edit, or delete any files unless I explicitly ask you to log results.
```

### T2 (Style, chat-only)

```text
Draft a customer email: we delay launch by one week because of a billing edge case; new target date is next Friday.
After your draft, state:
1. Which writing skill you applied (full name), or "none" if you did not use a writing skill.
2. Why you chose that skill (one or two sentences).
3. Whether any other skill also applied (domain or otherwise).

Show the result in chat only. Do not create, edit, or delete any files unless I explicitly ask you to log results.
```

### T3 (STE override)

```text
Rewrite the following email using simplified technical English (STE-inspired). Prefer writing-simplified-technical-english.

---
[paste soft email here]
---

After your draft, state:
1. Which writing skill you applied (full name), or "none" if you did not use a writing skill.
2. Why you chose that skill (one or two sentences).
3. Whether any other skill also applied (domain or otherwise).

Show the result in chat only. Do not create, edit, or delete any files unless I explicitly ask you to log results.
```

### T4 (Style override)

```text
Rewrite the following README blurb using Style clarity-and-grace principles. Prefer writing-clarity-and-grace.

---
[paste dry blurb here]
---

After your draft, state:
1. Which writing skill you applied (full name), or "none" if you did not use a writing skill.
2. Why you chose that skill (one or two sentences).
3. Whether any other skill also applied (domain or otherwise).

Show the result in chat only. Do not create, edit, or delete any files unless I explicitly ask you to log results.
```

### T5 (small-edit, chat-only)

```text
Fix ONLY this one sentence (do not rewrite the rest). Keep surrounding meaning.

Sentence to fix:
[paste one sentence]

Optional context (do not rewrite):
[paste surrounding paragraph]

After your draft, state:
1. Which writing skill you applied (full name), or "none" if you did not use a writing skill.
2. Why you chose that skill (one or two sentences).
3. Whether any other skill also applied (domain or otherwise).

Show the result in chat only. Do not create, edit, or delete any files unless I explicitly ask you to log results.
```

## Pass/fail rubrics (detail)

### T1 (STE positive)

- **Pass:** Prefer active voice; concrete verbs; limited synonym churn; protected tokens unchanged if present; self-report names STE (or equivalent full skill name).
- **Fail:** Long throat-clearing; marketing hype; external email tone; wrong/missing skill report when STE was expected.

### T2 (Style positive)

- **Pass:** Real actors as subjects; main point early; readable paragraphs; clear close; self-report names Style skill.
- **Fail:** STE-only telegram style with no audience shape; buried decision; empty openers kept; wrong/missing skill report.

### T3 / T4 (overrides)

- **Pass:** Stated skill/style clearly followed despite default context; self-report matches the override.
- **Fail:** Agent ignores the override and uses the other writing mode (prose or self-report).

### T5 (small-edit)

- **Pass:** Diff limited to the requested sentence (plus at most a trivial neighbor fix for grammar).
- **Fail:** Whole section or file restyled.

### T6 (ambiguous)

- **Pass:** One clarifying question, **or** a justified default with a short note of the assumption; self-report explains the choice.
- **Fail:** Confident wrong full rewrite with no signal.

### T7 (composition)

- **Pass:** Domain skill constraints/templates kept; wording improved; self-report mentions domain + writing roles when both apply.
- **Fail:** Writing skill replaces domain workflow or required structure.

### T8 (Style marketing)

- **Pass:** Benefit-led, concise, non-jargon; may use light emphasis; self-report names Style skill.
- **Fail:** Operator-manual STE; empty superlatives only.

## Where to record results

| Path | Use |
| --- | --- |
| [test-results/README.md](test-results/README.md) | How to name and fill result files |
| [test-results/_template.md](test-results/_template.md) | Copy for each run session |
| [test-results/](test-results/) | Actual run logs (one file per session recommended) |

Suggested filename: `YYYY-MM-DD_<agent>_T1-T5.md` (example: `2026-08-02_grok_T1-T5.md`).

## After failures

1. Adjust skill `description` trigger phrases and when/when-not sections.
2. Re-run the failed IDs only.
3. Note the change in `docs/STATUS.md` session log and keep the failing result file for comparison.
