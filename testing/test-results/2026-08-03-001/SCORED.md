# Trigger test run — scored — 2026-08-03-001

- **Date:** 2026-08-03
- **Agents:** Grok, Claude Code, Codex
- **Source transcripts:** this folder (`test1.md`, `test2.md`, `t3-*` … `t8-*`)
- **Skills discoverable?** yes (writing skills loaded when expected on T1–T4 and T6–T8 for all three agents)
- **Mode:** T1/T2 treated as **cold two-turn** (task-only turn 1, skill probe turn 2). T3–T4 **override (named skill)**. T6–T8 task-led.
- **Operator:** human-run chats; scoring by agent against `testing/TRIGGER-TESTS.md`
- **Fixture note:** T1/T2 transcripts used `skills-testing` paths (`readme.md`, `email-briefing.md`). Content is warehouse / launch-delay domain (not skill-meta). T3–T8 used `testing/testing-files/` where present.
- **T5:** not present in this run folder → **skip** for all agents.
- **Rescore:** 2026-08-03 — Codex `t4` / `t6` / `t7` fixed; Codex `t8` retested → Style pass (was marketing-skills weak pass).

## Summary matrix

| ID | Grok | Claude | Codex | Expected | Mode |
| --- | --- | --- | --- | --- | --- |
| T1 | **pass (strong)** | **pass (strong)** | **pass (strong)** | STE | cold two-turn |
| T2 | **pass (strong)** | **pass (strong)** | **pass (strong)** | Style | cold two-turn |
| T3 | **pass** | **pass** | **pass** | STE override | warm / named |
| T4 | **pass** | **pass** | **pass** | Style override | warm / named |
| T5 | skip | skip | skip | small-edit | — |
| T6 | **pass** | **pass** | **pass** | ask / justified default | optional |
| T7 | **pass** | **pass** | **pass** | domain + polish | optional |
| T8 | **pass** | **pass** | **pass** | Style not STE | optional |

**Cold auto-invoke (T1 + T2 strong pass):** **yes** — all three agents  
**Phase 3 gate (cold T1+T2 on ≥1 agent):** **met**  
**T1–T5 full row this batch:** incomplete only for **T5 missing** (T1–T4 all pass ×3 agents)

---

## T1 — auto STE (cold)

**Sources:** `test1.md`  
**Expected:** `writing-simplified-technical-english`

### Grok — **pass (strong)**

| Signal | Finding |
| --- | --- |
| Turn 1 skill load UI | Yes — `writing-simplified-technical-english` (`~\.grok\skills\…`) |
| Turn 1 prose | Yes — numbered imperative steps; active voice; concrete verbs (get, log in, set, restart) |
| Turn 2 claim | Yes — same skill; path quoted |

**Excerpt:** numbered Getting started; “Ask an administrator… / Log in… / Set the default warehouse…”

### Claude — **pass (strong)**

| Signal | Finding |
| --- | --- |
| Turn 1 skill load UI | Yes — `writing-simplified-technical-english` |
| Turn 1 prose | Yes — active/imperative; concrete verbs; procedure shape |
| Turn 2 claim | Yes — skill id + path |

**Notes:** Mentions STE principles in turn-1 output (after skill load — fine for scoring; not user-primed).

### Codex — **pass (strong)**

| Signal | Finding |
| --- | --- |
| Turn 1 skill load UI | Yes — announced STE skill; path on probe |
| Turn 1 prose | Yes — short active steps; consistent terms |
| Turn 2 claim | Yes — full path to `writing-simplified-technical-english` |

---

## T2 — auto Style (cold)

**Sources:** `test2.md`  
**Expected:** `writing-clarity-and-grace`

### Grok — **pass (strong)**

| Signal | Finding |
| --- | --- |
| Turn 1 skill load UI | Yes — Style skill before draft |
| Turn 1 prose | Yes — point early (delay + next Friday); actors; clear close / no action required |
| Turn 2 claim | Yes — Style path + id |

### Claude — **pass (strong)**

| Signal | Finding |
| --- | --- |
| Turn 1 skill load UI | Yes — `writing-clarity-and-grace` |
| Turn 1 prose | Yes — decision + reason; next step; no invented facts beyond placeholders |
| Turn 2 claim | Yes |

### Codex — **pass (strong)**

| Signal | Finding |
| --- | --- |
| Turn 1 skill load UI | Claimed on probe with Style path (load on turn 1 plausible from prose) |
| Turn 1 prose | Yes — delay early; billing edge case; next Friday; no action required |
| Turn 2 claim | Yes — Style SKILL.md path |

---

## T3 — STE override

**Sources:** `t3-grok.md`, `t3-claude.md`, `t3-codex.md`  
**Expected:** STE despite email genre (override wins)

### Grok — **pass**

- Load / claim: `writing-simplified-technical-english`
- Prose: short sentences, actor early, filler removed; still polite email
- Override honored

### Claude — **pass**

- Load / claim: STE; explicitly notes email is usually “when not” but **user request outranks**
- Prose: one idea per sentence; concrete verbs
- Strong override behavior (documents composition correctly)

### Codex — **pass**

- Load / claim: STE path
- Prose: short active sentences; less soft/vague than source

---

## T4 — Style override

**Sources:** `t4-grok.md`, `t4-claude.md`, `t4-codex.md`  
**Expected:** Style on dry blurb

### Grok — **pass**

- Load / claim: `writing-clarity-and-grace`
- Prose: actors/actions; old→new flow; not STE telegram list

### Claude — **pass**

- Load / claim: Style
- Prose: merged choppy lines; real actors; cohesion

### Codex — **pass**

- Load / claim: `writing-clarity-and-grace` (path under `skills/`)
- Prose: grouped capabilities; direct actions; config→restart order; not STE telegram one-liners
- Override honored; facts preserved (modules, config, restart, stock counts, DB)

---

## T5 — small-edit

**Result (all agents):** **skip** — no transcript in `2026-08-03-001/`.

---

## T6 — mixed update (optional)

**Sources:** `t6-grok.md`, `t6-claude.md`, `t6-codex.md`  
**Expected:** Clarifying question **or** justified default; no silent wrong full style swap

### Grok — **pass**

- Loaded **both** writing skills; led with Style for mixed audience; light STE on tech terms
- Justified default in probe; clear multi-block rewrite (sync / API / next steps)
- Not a silent wrong full swap

### Claude — **pass**

- Load / claim: Style only
- Prose: actors, cut hedges, split by topic
- Reasonable default for “make clearer” mixed note

### Codex — **pass**

- Loaded **both** writing skills; **draft via STE** (justified: “in-repository technical update”)
- Prose: short active blocks (sync / reporting lag / 429+backoff / next share); clearer than source
- Not a silent wrong full swap — default stated and explained
- **Note:** Grok/Claude defaulted Style for mixed audience; Codex defaulted STE for in-repo technical. Both allowed by rubric (justified default)

---

## T7 — domain summary (optional)

**Sources:** `t7-grok.md`, `t7-claude.md`, `t7-codex.md` (also `t7-Codex.md` if present — same case)  
**Expected:** Facts preserved; wording improved

### Fact checklist (fixture)

| Fact | Grok | Claude | Codex |
| --- | --- | --- | --- |
| 12,840 rows | yes | yes | yes |
| 17 failures | yes | yes | yes |
| 12 DUPLICATE_SKU / 5 MISSING_LOCATION | yes | yes | yes |
| ~14 min / 842 s | yes (~14 min) | yes (~14 min) | yes (842 s) |
| operator j.martinez | yes | yes | yes (J. Martinez) |
| re-run twice; lock aisle B | yes | yes | yes |
| numbers may omit retries | yes | yes | yes |
| recommendation empty / next TBD | yes | yes | yes |

### Grok — **pass**

- Style skill; structure scannable; no invented metrics

### Claude — **pass**

- Style skill; surfaces open questions (retries, no owner for next action)

### Codex — **pass**

- Load / claim: `writing-clarity-and-grace`
- Prose: outcome first, failures, operational uncertainty, unresolved next step
- All required facts preserved; no invented recommendation

---

## T8 — landing blurb (optional)

**Sources:** `t8-grok.md`, `t8-claude.md`, `t8-Codex` (extensionless transcript; retest)  
**Expected:** Style (benefit-led), **not** STE procedure; only facts from fixture

### Grok — **pass**

- Load: `writing-clarity-and-grace`
- Benefit-led; live counts / alerts / CSV / scanners; no pricing/logos

### Claude — **pass**

- Load: Style
- Benefit-led; discarded vague “sophisticated methodologies” line; audience close

### Codex — **pass** (retest)

| Signal | Finding |
| --- | --- |
| Turn 1 skill load | Yes — announced **writing-clarity-and-grace** for customer-facing landing copy |
| Turn 1 prose | Yes — problem-first (“Stop missing reorders”); live stock / email alerts / CSV / scanners; facts only; not STE procedure |
| Turn 2 claim | Yes — `skills/writing-clarity-and-grace/SKILL.md` |

**Prior attempt (superseded):** first log used `marketing-skills:copywriting` → weak pass (routing). Retest uses Style; score **pass**.

---

## Phase 3 acceptance (from TRIGGER-TESTS.md)

| Criterion | Status |
| --- | --- |
| T1–T5 pass on ≥1 agent | **Partial this batch** — T1–T4 **pass ×3 agents**; **T5 not run here**; prior supervised T5 on Grok in `2026-08-02_grok_T1-T5.md` |
| Cold auto-invoke T1 and T2 on ≥1 agent | **Met** (all three) |
| Results under `testing/test-results/` | **Yes** (this folder + SCORED.md) |
| Failures → skill fix or accepted limitation | T6 default STE vs Style is acceptable variance. T8 Codex routing issue resolved on retest |

---

## Follow-ups

1. **Run T5** (all agents) for small-edit discipline — only open gap in this matrix.
2. Prefer fixtures under `testing/testing-files/` for future cold T1/T2 so paths match the matrix (content was already domain-neutral).
3. Optional: rename extensionless `t8-Codex` → `t8-codex.md` for consistent naming.

## Linkage

- Protocol: [../../TRIGGER-TESTS.md](../../TRIGGER-TESTS.md)
- Prior supervised Grok T1–T5: [../2026-08-02_grok_T1-T5.md](../2026-08-02_grok_T1-T5.md)
