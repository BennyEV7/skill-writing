# Trigger test run — TEMPLATE

Copy this file to `YYYY-MM-DD_<agent>_<scope>.md` and fill it in.

- **Date:** YYYY-MM-DD
- **Agent:** (Grok / Claude Code / Codex / other)
- **Agent version / model (if known):**
- **Skills discoverable?** yes / no / unknown
- **Mode:** cold (two-turn) / same-thread warm / supervised
- **Operator:**

## Summary

| ID | Result | Mode | Skill claimed (turn 2) | Skill load UI (turn 1) | Skill expected | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| T1 | pass / weak pass / fail / skip / inconclusive | | | | STE | |
| T2 | pass / weak pass / fail / skip / inconclusive | | | | Style | |
| T3 | pass / fail / skip | | | | STE override | |
| T4 | pass / fail / skip | | | | Style override | |
| T5 | pass / fail / skip | | | | small-edit | |
| T6 | pass / fail / skip | | | | | optional |
| T7 | pass / fail / skip | | | | | optional |
| T8 | pass / fail / skip | | | | | optional |
| T9 | pass / fail / skip | | | | Style long-form | |

**Cold auto-invoke (T1 + T2 strong pass on this agent):** yes / no / partial  
**Phase 3 gate note:** (e.g. strong cold T1–T2, or only warm/supervised)

## Cases

### T1

- **Result:** pass / weak pass / fail / skip / inconclusive
- **Mode:** cold two-turn / warm / supervised
- **Turn 1 — skill load UI (if any):**
- **Turn 1 — prose matches expected style?** yes / no
- **Turn 2 — skill claimed (quote):**
- **Turn 2 — why claimed (quote):**
- **Other skills claimed:**
- **Notes:**
- **Draft excerpt (optional):**

### T2

- **Result:** pass / weak pass / fail / skip / inconclusive
- **Mode:** cold two-turn / warm / supervised
- **Turn 1 — skill load UI (if any):**
- **Turn 1 — prose matches expected style?** yes / no
- **Turn 2 — skill claimed (quote):**
- **Turn 2 — why claimed (quote):**
- **Other skills claimed:**
- **Notes:**
- **Draft excerpt (optional):**

### T3

- **Result:** pass / fail / skip
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Other skills claimed:**
- **Prose matches expected style?** yes / no
- **Notes:**
- **Excerpt (optional):**

### T4

- **Result:** pass / fail / skip
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Other skills claimed:**
- **Prose matches expected style?** yes / no
- **Notes:**
- **Excerpt (optional):**

### T5

- **Result:** pass / fail / skip
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Other skills claimed:**
- **Only requested span changed?** yes / no
- **Notes:**
- **Excerpt (optional):**

### T6 (optional)

- **Result:** pass / fail / skip
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Notes:**

### T7 (optional)

- **Result:** pass / fail / skip
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Domain structure preserved?** yes / no
- **Notes:**

### T8 (optional)

- **Result:** pass / fail / skip
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Notes:**

### T9

- **Result:** pass / fail / skip
- **Mode:** cold / warm / supervised
- **Skill claimed (quote):**
- **Why claimed (quote):**
- **Facts preserved?** yes / no
- **Sustained argument?** yes / no
- **Developed paragraphs?** yes / no
- **Varied cadence?** yes / no
- **Presentation-slide prose avoided?** yes / no
- **Notes:**

## Follow-ups

- Skill description changes needed?
- Accepted limitations?
- Link to commit if skills were changed after this run:
