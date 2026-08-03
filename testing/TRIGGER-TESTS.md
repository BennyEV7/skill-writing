# Trigger tests — writing skills

**Purpose:** Measure whether agents pick the right writing skill and follow small-edit / override rules.  
**Last updated:** 2026-08-03

Skills under test:

- `writing-simplified-technical-english` (STE)
- `writing-clarity-and-grace` (Style)

**Layout:**

| Path | Purpose |
| --- | --- |
| [testing-files/](testing-files/) | Clunky **neutral** fixtures (fictional warehouse product — not about writing skills) |
| [test-results/](test-results/) | Scored run logs |
| [README.md](README.md) | This folder’s map |

Using fixtures about writing skills can prime agents and hide cold-start failures. Prefer [testing-files/](testing-files/).

## Phase 3 acceptance criteria

Phase 3 **passes** when:

1. Cases **T1–T5** pass on at least **one** agent.
2. For **auto-invoke** claims (T1, T2), at least one agent has a **cold-start** pass (see protocol below), not only a same-thread or same-message self-report run.
3. Results are recorded under `testing/test-results/`.
4. Failures either get a skill-description / when-not fix, or an explicit “accepted limitation” note in `docs/STATUS.md`.

Optional stretch: T6–T8 and multi-agent rows.

Supervised or same-thread runs are useful for application quality but **do not** alone prove cold auto-invocation.

---

## Cold start vs warm context

| Mode | What it is | Proves | Does not prove |
| --- | --- | --- | --- |
| **Cold start** | Fresh session; **turn 1 = task only** (no skill names, no self-report block) | Auto-invocation / default routing under realistic user wording | — |
| **Warm / same-thread** | T2+ after T1 in one chat, or self-report in the same message as the task | Application once primed; overrides; small-edit | Clean auto-invoke |
| **Supervised** | Operator or docs already named the expected skill | Skill content quality | Discovery |

**Do not** put the skill self-report in the **same message** as a cold-start task.

**Do not** use source text about “writing skills,” STE, or this repo’s skill pack for cold T1/T2 fixtures.

---

## Official protocol: two-turn cold start (T1, T2)

| Turn | Purpose | Content |
| --- | --- | --- |
| **1** | Cold task | Only the real user request + optional “chat only / no file edits.” **No** skill names or self-report. |
| **2** | Probe routing | Ask which writing skill was applied (follow-up only). |
| **3** (optional) | Logging | Write a results file under `testing/test-results/` or a staging folder. |

### Recommended session layout (per agent)

1. **Fresh session A:** T1 only (turns 1–2) — cold auto STE  
2. **Fresh session B:** T2 only (turns 1–2) — cold auto Style  
3. **One warm thread (optional):** T3 → T4 → T5 — overrides + small-edit  

Label same-thread runs `…_same-thread` or `…_warm`.

### Turn 1 — cold task only

#### T1 (auto STE)

Point the agent at the fixture (open the file or paste its path). Prefer working in a copy of the fixture content, not this skill-writing README.

```text
Rewrite the Getting started section of readme.md in clear technical English.
Show the result in chat only. Do not create, edit, or delete any files.
```

#### T2 (auto Style)

```text
Using only the facts in email-briefing.md, draft a customer email about the launch delay.
Show the result in chat only. Do not create, edit, or delete any files.
```

### Turn 2 — skill probe (after the draft)

```text
About the draft you just wrote:

1. Which writing skill did you apply (full name), or "none" if you did not use a writing skill?
2. Why did you choose that (one or two sentences)?
3. Did any other skill also apply (domain or otherwise)?

Answer those three points only. Do not rewrite the draft unless I ask.
```

Optional tighter probe:

```text
Before explaining: did you load or open any skill file for that draft? If yes, name the path or skill id. If no, say "none".
Then briefly say why you wrote it the way you did.
Do not rewrite the draft unless I ask.
```

### What to keep out of cold turn 1

- “writing skill”, skill slash-names, “STE”, “Style: …”
- “After your draft, state which skill…”
- Test matrix language (“T1”, “cold start”, “pass/fail”)
- Source text that discusses agent skills or this test harness

---

## Warm / override protocol (T3, T4, T5)

Overrides **should** name the skill or style on turn 1. Self-report may be turn 2.

---

## How to run a case (checklist)

1. Choose mode: **cold** (T1/T2 auto) or **warm** (overrides / same-thread).
2. Use fixtures under `testing/testing-files/` (neutral domain).
3. Skills must already be discoverable. No installer.
4. Prefer **chat-only** drafts.
5. Cold: turn 1 task → turn 2 probe.
6. Note **UI skill load** on turn 1 when visible.
7. Score prose (turn 1) and claim (turn 2) separately.
8. Save under `testing/test-results/`; name files with mode (`_cold`, `_same-thread`, etc.).

---

## Matrix

| ID | Fixture | Expected skill | Cold? | Acceptance signal |
| --- | --- | --- | --- | --- |
| T1 | `testing-files/t1-readme-getting-started.md` | STE | **Yes** | Short active sentences; consistent terms; no marketing voice |
| T2 | `testing-files/t2-email-briefing.md` | Style | **Yes** | Actor/action; point early; clear next step/ask |
| T3 | `testing-files/t3-soft-email.md` | STE override | No | Override wins; more plain/procedural than Style |
| T4 | `testing-files/t4-dry-blurb.md` | Style override | No | Override wins; flow/emphasis without pure STE flatness |
| T5 | `testing-files/t5-module-description.md` | STE + small-edit | No | Only the first body sentence changes |
| T6 | `testing-files/t6-mixed-update.md` | Ask or context default | Optional cold | No silent wrong full style swap |
| T7 | `testing-files/t7-domain-summary-raw.md` | Domain structure + writing polish | Warm OK | Facts preserved; prose improved |
| T8 | `testing-files/t8-product-facts.md` | Style, not STE | Optional cold | Benefit-led blurb; not robotic procedure |

---

## Ready-to-paste shells

### T1 / T2 cold

See [Turn 1](#turn-1--cold-task-only) and [Turn 2](#turn-2--skill-probe-after-the-draft) above.

### T3 (STE override) — turn 1

```text
Rewrite the email in testing/testing-files/t3-soft-email.md using simplified technical English (STE-inspired). Prefer writing-simplified-technical-english.
Show the result in chat only. Do not create, edit, or delete any files.
```

Then optional Turn 2 skill probe.

### T4 (Style override) — turn 1

```text
Rewrite the blurb in testing/testing-files/t4-dry-blurb.md using Style clarity-and-grace principles. Prefer writing-clarity-and-grace.
Show the result in chat only. Do not create, edit, or delete any files.
```

Then optional Turn 2 skill probe.

### T5 (small-edit) — turn 1

```text
In testing/testing-files/t5-module-description.md, fix ONLY this one sentence (do not rewrite the rest). Keep surrounding meaning.

Sentence to fix:
This module is responsible for the facilitation of connection management and performs handling of retries in the event that network failures are encountered.

Show the result in chat only. Do not create, edit, or delete any files.
```

Then Turn 2 skill probe.

### T6 — turn 1 (optional cold)

```text
Make the text in testing/testing-files/t6-mixed-update.md clearer.
Show the result in chat only. Do not create, edit, or delete any files.
```

### T7 — turn 1

```text
Write a clear short summary for leadership from testing/testing-files/t7-domain-summary-raw.md. Keep the facts; improve the wording only.
Show the result in chat only. Do not create, edit, or delete any files.
```

### T8 — turn 1 (optional cold)

```text
Write a short landing-page blurb using only the facts in testing/testing-files/t8-product-facts.md.
Show the result in chat only. Do not create, edit, or delete any files.
```

---

## Scoring

### Signals (priority order)

1. **UI / tool: skill loaded on turn 1** (if shown)  
2. **Turn 1 prose** vs expected style  
3. **Turn 2 self-report** — can be retroactive; trust less than UI + prose  

### Combined outcomes (T1 / T2 cold)

| Turn 1 prose | Skill load UI (if any) | Turn 2 claim | Score |
| --- | --- | --- | --- |
| Matches expected | Right skill | Matches | **Pass** (strong) |
| Matches expected | Right skill | Wrong / none | **Pass** (behavior); note claim noise |
| Matches expected | None / unknown | Correct name | **Weak pass** |
| Matches expected | None / unknown | none | **Weak pass / inconclusive** |
| Wrong style | — | — | **Fail** |
| Matches expected | Wrong skill | — | **Fail** (routing) |

### Rubrics by case

#### T1 (STE)

- **Pass:** Active voice; concrete verbs; limited synonym churn; cold routing evidence.  
- **Fail:** Marketing/email voice; wrong skill load; wrong style on turn 1.

#### T2 (Style)

- **Pass:** Real actors; main point early; clear close; cold routing evidence.  
- **Fail:** STE-only telegram; buried decision; wrong skill load.

#### T3 / T4 (overrides)

- **Pass:** Named skill/style followed; claim matches override.  
- **Fail:** Ignores override.

#### T5 (small-edit)

- **Pass:** Only the target sentence changes (plus trivial neighbor grammar at most).  
- **Fail:** Whole file restyled.

#### T6

- **Pass:** Clarifying question or justified default.  
- **Fail:** Confident wrong full rewrite with no signal.

#### T7

- **Pass:** Facts/numbers preserved; wording improved.  
- **Fail:** Invented metrics or dropped required facts.

#### T8

- **Pass:** Benefit-led, concise; light emphasis OK.  
- **Fail:** Operator-manual STE; empty superlatives only.

---

## Where to record results

| Path | Use |
| --- | --- |
| [test-results/README.md](test-results/README.md) | Naming and fill instructions |
| [test-results/_template.md](test-results/_template.md) | Copy per run |
| [test-results/](test-results/) | Actual logs |

Suggested filenames: `YYYY-MM-DD_<agent>_T1-cold.md`, `…_T1-T5-same-thread.md`, etc.

Staging from another repo (e.g. `skills-testing/results/`): copy into `testing/test-results/` and note mode.

---

## After failures

1. Adjust skill `description` trigger phrases and when/when-not sections.  
2. Re-run failed IDs with the **same mode** (cold failures → cold retest).  
3. Note in `docs/STATUS.md`; keep failing result files for comparison.
