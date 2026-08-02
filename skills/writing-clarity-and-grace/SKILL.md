---
name: writing-clarity-and-grace
description: >
  Write and revise external, people-facing communication using clarity and
  grace principles (actors as subjects, actions as verbs, old-to-new flow,
  cohesion, concision, emphasis, shape, audience fit). Inspired by practices
  taught in Style: Ten Lessons in Clarity and Grace — original agent checklists
  only, not book text. Use for emails, Slack/Teams messages, stakeholder
  updates, blog posts, articles, marketing and landing copy, announcements,
  customer support replies, sales messages, and any writing outside a project
  repo. Trigger phrases: "write an email", "draft a message", "stakeholder
  update", "blog post", "landing page", "announcement", "customer reply",
  "sales email", "make this clearer", "clarity and grace", "Style principles",
  "external communication", "rewrite for readers". Do not use for in-repo
  technical docs, procedures, commits, or manuals (use
  writing-simplified-technical-english instead). Slash command:
  /writing-clarity-and-grace
---

# Writing: Clarity and Grace (Style-inspired)

## Purpose

Produce **clear, readable, audience-fit prose** for **external communication**.

This skill encodes **original agent instructions** based on well-known clarity
principles popularized by *Style: Ten Lessons in Clarity and Grace*
(Williams/Bizup). It does **not** reproduce the book’s lesson text.

## Priority (highest first)

1. Explicit user request (tone, brand, length, or “keep my voice”)
2. Project or brand guidelines if the user points to them
3. This skill

## Composition with other skills

- **Domain skills** own facts, workflow, tools, and task structure (for example support macros with required fields, sales CRM steps, SEO audit checklists).
- **This writing skill** owns prose quality only: clarity, cohesion, emphasis, shape, and audience fit.
- If a domain skill is active: follow its workflow first. Apply clarity principles to the **wording of deliverables**, not to override domain constraints or required sections.
- Fill required templates in this writing style. Do not replace the template.
- If both writing skills could apply: user request > project/brand rules > **writing-simplified-technical-english** for in-repo technical prose; this skill for external people-facing prose.

## When to use

- Emails, DMs, Slack/Teams, stakeholder updates
- Blog posts, articles, newsletters
- Marketing, landing pages, announcements, launch notes for people
- Customer support and sales replies
- Any writing **not** primarily in-repo technical documentation

## When NOT to use

- README, architecture, STATUS/PLAN, runbooks, API/help manuals
- Comments, docstrings, commit messages, PR descriptions as engineering artifacts
- Step-by-step operator procedures that need STE-like consistency
- Small edits where matching the existing text matters more than a full polish

If the task is in-project technical prose, load **writing-simplified-technical-english** instead.

## Default if unsure

- **Outside** a repo or clearly external audience → this skill  
- **Inside** a repo on technical docs/code prose → writing-simplified-technical-english  
- Still unsure → ask one short question

## Intensity by genre

| Genre | Intensity |
| --- | --- |
| Stakeholder email / status note | Clarity + concision; warm but direct |
| Blog / article | Full shape: open, point, develop, close |
| Marketing / landing | Clarity first; allow emphasis, rhythm, and CTA; not STE-flat |
| Support reply | Empathy + clear next step; short paragraphs |
| Sales | Reader benefit early; one ask; no hype fog |

## Core principles (agent checklist)

Apply as a **diagnose → revise** loop. Do not lecture the user about the book.

### 1. Characters and actions

- Put the **real actor** in the subject position  
- Put the **real action** in the verb  
- Prefer “The team decided…” over “A decision was made…”

### 2. Name the action (cut hollow nouns)

- When a noun hides a verb, restore the verb if it clarifies:  
  *decision → decide*, *analysis → analyze*, *implementation → implement*
- Keep a noun when it is the true topic (“The decision stands.”)

### 3. Old → new information

- Start sentences with **familiar context**  
- End with **new, important, or stressed** information  
- Avoid dumping novelty in the first three words unless for punch in marketing

### 4. Cohesion

- Connect sentence starts to what came before (same topic thread)  
- Use light transitions only when the jump is real  
- Prefer topic continuity over decorative connectors (*furthermore*, *moreover*)

### 5. Concision

Delete or rewrite:

- Doubled words (*each and every*, *first and foremost*)
- Empty openers (*It is important to note that*, *The fact that*)
- Hedges stacked without need (*somewhat*, *various*, *potentially* ×3)
- Metadiscourse that adds no value (*In this email I will…*)

### 6. Emphasis

- Put the stress at the **end** of the sentence or paragraph  
- Keep the main claim out of a weak trailing clause  
- One primary emphasis per sentence

### 7. Shape

- **Open** with why the reader should care (one beat)  
- State the **point early** (not after a long wind-up)  
- **Develop** with short paragraphs (often 2–4 sentences)  
- **Close** with the ask, next step, or takeaway  

### 8. Audience fit

- Match formality to the relationship  
- Prefer reader benefits and concrete outcomes over writer process  
- For marketing: clarity + energy; avoid vague superlatives without proof  
- For support: acknowledge → answer → action  

## Revise checklist

Before finishing, scan for:

- [ ] Abstract subjects (*consideration*, *utilization*) where a person/system should act
- [ ] Nominalizations that smother the action
- [ ] New information dumped before context
- [ ] Broken topic flow between sentences
- [ ] Empty openers and stacked hedges
- [ ] Main point buried; weak endings
- [ ] Wrong length for the channel (essay-length Slack message, etc.)
- [ ] Full rewrite when only a small edit was requested

## Before / after examples

### Email

**Before:**  
It is important to note that consideration has been given to the prioritization of the roadmap and a decision has been made that a delay will be necessary.

**After:**  
We reviewed the roadmap and decided to delay the release by two weeks.  
The payment API integration is the blocker. I will send a revised date on Friday.

### Stakeholder update

**Before:**  
Regarding the various ongoing efforts that are currently being undertaken by the team, progress is being made in a number of areas.

**After:**  
This week the team finished the billing export and started load tests.  
Next week we aim to ship the export to staging. The risk is third-party API rate limits.

### Support reply

**Before:**  
Your issue has been looked into and it was found that the problem is related to cache settings which should be adjusted.

**After:**  
Thanks for the report — you hit a cache settings issue.  
Please set `CACHE_TTL` to `60` and restart the app. If it still fails, send the last 20 log lines and I will dig further.

### Landing blurb (clarity + light persuasion)

**Before:**  
Our solution utilizes a sophisticated methodology in order to facilitate optimization of your workflow paradigms.

**After:**  
Stop losing hours to copy-paste updates.  
Our tool turns project notes into a weekly status email in one click.

## Small-edit rule

If the user asks to tighten one paragraph or fix tone in one place:

- **Do not** rewrite the entire piece unless asked  
- Preserve the user’s voice when they have a clear voice already  

## Optional depth

For denser revision moves and more examples, open:

- `references/rules-cheatsheet.md`
- `references/examples.md`

Only open these for long drafts or weak first passes.

## What not to claim

- Do **not** paste or paraphrase the book chapter-by-chapter  
- Do **not** say the output “follows Williams lesson N”  
- You may say “clearer, more direct prose” or “revised for clarity and flow”
