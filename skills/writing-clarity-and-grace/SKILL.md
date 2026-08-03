---
name: writing-clarity-and-grace
description: >
  Write and revise external, people-facing communication using clarity and
  grace principles (actors as subjects, actions as verbs, old-to-new flow,
  cohesion, concision, emphasis, shape, audience fit). Inspired by practices
  taught in "Style: Ten Lessons in Clarity and Grace" Use for emails, Slack/Teams messages, stakeholder updates, blog posts, articles, marketing and landing copy, announcements, customer support replies, sales messages, and any writing outside a project repo. Trigger phrases: "write an email", "draft a message", "stakeholder
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
principles popularized by _Style: Ten Lessons in Clarity and Grace_
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

**Applies regardless of starting material.** Revising an existing draft and writing new prose from raw facts, notes, quotes, transcripts, or bullet points are both in scope. The output's audience and purpose decide the skill, not whether a draft already exists.

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

## Mixed audience default

Some content serves both a technical and a non-technical audience in one piece (for example, a status update that mixes API details for engineers with a timeline note for stakeholders).

- Default to **this skill** for overall structure, tone, and flow.
- Keep technical clauses precise. Do not soften or generalize facts, error codes, config values, or numbers to fit a lighter tone.
- State the default briefly if the user did not ask for one style (for example: "structured for a mixed audience; kept technical details precise").
- If the piece is primarily an in-repo technical artifact with only a short human note attached (for example, a PR description), prefer **writing-simplified-technical-english** instead and say so.

Use one stated default instead of improvising a different split each time.

## Intensity by genre

| Genre                           | Intensity                                                    |
| ------------------------------- | ------------------------------------------------------------ |
| Stakeholder email / status note | Clarity + concision; warm but direct                         |
| Blog / article                  | Full shape: open, point, develop, close                      |
| Marketing / landing             | Clarity first; allow emphasis, rhythm, and CTA; not STE-flat |
| Support reply                   | Empathy + clear next step; short paragraphs                  |
| Sales                           | Reader benefit early; one ask; no hype fog                   |

## Core principles (agent checklist)

Apply as a **diagnose → revise** loop. Do not lecture the user about the book.

### 1. Characters and actions

- Put the **real actor** in the subject position
- Put the **real action** in the verb
- Prefer “The team decided…” over “A decision was made…”
- Passive and nominalized phrasing are still the right call sometimes: actor unknown or unimportant, keeping the same topic running across sentences, or deliberately pushing stress to the sentence's end. Don't strip them on reflex.

### 2. Name the action (cut hollow nouns)

- When a noun hides a verb, restore the verb if it clarifies:  
  _decision → decide_, _analysis → analyze_, _implementation → implement_
- Keep a noun when it is the true topic (“The decision stands.”)

### 3. Old → new information

- Start sentences with **familiar context**
- End with **new, important, or stressed** information
- Avoid dumping novelty in the first three words unless for punch in marketing

### 4. Cohesion

- Connect sentence starts to what came before (same topic thread)
- Use light transitions only when the jump is real
- Prefer topic continuity over decorative connectors (_furthermore_, _moreover_)
- Across the whole piece, call one entity by one name (don't drift between "the team," "they," and "engineering" for the same actor); restate a section's point before you subdivide it

### 5. Concision

Delete or rewrite:

- Doubled words (_each and every_, _first and foremost_)
- Empty openers (_It is important to note that_, _The fact that_)
- Hedges stacked without need (_somewhat_, _various_, _potentially_ ×3)
- Metadiscourse that adds no value (_In this email I will…_)

### 6. Emphasis

- Put the stress at the **end** of the sentence or paragraph
- Keep the main claim out of a weak trailing clause
- One primary emphasis per sentence
- Use a cleft ("What changed is…", "It was the API limit that…") or a trailing modifier to land stress deliberately, not just default word order (see `references/rules-cheatsheet.md` for the fuller device list)

### 7. Shape

- **Open** with why the reader should care (one beat)
- State the **point early** (not after a long wind-up)
- **Develop** with short paragraphs (often 2–4 sentences)
- **Close** with the ask, next step, or takeaway
- For longer pieces, structure around problem → response → so-what, not just open/point/develop/close

### 8. Audience fit

- Match formality to the relationship
- Prefer reader benefits and concrete outcomes over writer process
- For marketing: clarity + energy; avoid vague superlatives without proof
- For support: acknowledge → answer → action

### 9. Fidelity and honesty

- Keep every claim attached to whoever actually said or believed it in the source.
- Do not turn a third party's quoted characterization, hedge, guess, or open question into the subject's own confident statement.
- If the source marks something as unresolved, contested, or provisional, keep that status. Do not resolve it for them.
- Don't use vagueness, passive voice, or stacked hedges to blur who owns bad news, or to inflate a claim past what the facts support. Clarity is a courtesy to the reader; don't spend it on obscuring instead of informing.

### 10. Elegance

- Vary sentence length and rhythm; a run of same-length sentences reads flat
- Give parallel items parallel grammar (all nouns, or all verbs, not a mix)
- Don't swap in a synonym for the same referent just to avoid repeating a word ("elegant variation") — it makes the reader wonder if you mean something different

### 11. Correctness without folklore

- Fix real errors: subject-verb agreement, dangling modifiers, unclear pronoun reference
- Leave classroom folklore alone unless house style demands it: split infinitives, sentence-final prepositions, "which" only for nonrestrictive clauses, and starting a sentence with "and" or "but" are not errors
- See `references/rules-cheatsheet.md` for the real-vs-folklore table

## Revise checklist

Before finishing, scan for:

- [ ] Abstract subjects (_consideration_, _utilization_) where a person/system should act
- [ ] Nominalizations that smother the action
- [ ] New information dumped before context
- [ ] Broken topic flow between sentences
- [ ] Empty openers and stacked hedges
- [ ] Main point buried; weak endings
- [ ] Wrong length for the channel (essay-length Slack message, etc.)
- [ ] Full rewrite when only a small edit was requested
- [ ] A source's hedge, question, or someone else's characterization rewritten as the subject's own confident claim
- [ ] Same entity named the same way throughout (no drifting labels for one actor or system)
- [ ] Passive voice or a nominalization kept only where it earns its place (unknown actor, topic continuity, deliberate stress shift)
- [ ] Vagueness or hedging isn't hiding who owns bad news or inflating a claim
- [ ] Folklore grammar rules not "corrected" into stiffness

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
Thanks for the report. You hit a cache settings issue.  
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

- `references/rules-cheatsheet.md` — common rewrites, channel lengths, tone dials, emphasis devices (cleft sentences, resumptive/summative/free modifiers), extended concision patterns, correctness real-vs-folklore table, and elegance examples
- `references/examples.md`

Only open these for long drafts or weak first passes.

## What not to claim

- Do **not** paste or paraphrase the book chapter-by-chapter
- Do **not** say the output “follows Williams lesson N”
- You may say “clearer, more direct prose” or “revised for clarity and flow”
