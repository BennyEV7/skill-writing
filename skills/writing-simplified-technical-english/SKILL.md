---
name: writing-simplified-technical-english
description: >
  Write and revise in-project technical prose using Simplified Technical English
  (STE) inspired principles from ASD-STE100 practice — short clear sentences,
  consistent terminology, active voice, and procedural clarity. Use for repo
  docs (README, STATUS, PLAN, architecture), comments, docstrings, commit
  messages, PR descriptions, API/help/manual content, and other technical
  writing inside a software project. Trigger phrases: "use STE", "simplified
  technical English", "STE writing", "technical docs style", "write the README",
  "update STATUS", "document this", "PR description", "commit message",
  "user manual", "help text", "docstring", "in-repo docs". Do not use for
  external email, marketing, blog posts, or customer sales copy (use
  writing-clarity-and-grace instead). Slash command: /writing-simplified-technical-english
---

# Writing: Simplified Technical English (STE-inspired)

## Purpose

Produce **clear, consistent technical English** for work **inside projects**.

This skill is **inspired by ASD-STE100** practices. It is **not** certified
ASD-STE100 compliance and does **not** include the official controlled dictionary.

## Priority (highest first)

1. Explicit user request (style, tone, or “ignore STE”)
2. Project `AGENTS.md` / project writing rules
3. This skill

## Composition with other skills

- **Domain skills** own facts, workflow, tools, and task structure (for example SEO audits, PR babysitting, spreadsheets).
- **This writing skill** owns prose quality only: sentence shape, terminology consistency, and technical clarity.
- If a domain skill is active: follow its workflow first. Apply STE-inspired wording to **deliverables**, not to override domain steps, schemas, or required templates.
- Fill required templates in this writing style. Do not replace the template.
- If both writing skills could apply: user request > project rules > this skill for in-repo technical prose; use **writing-clarity-and-grace** for external people-facing prose.

## When to use

- README, architecture, STATUS, PLAN, runbooks, ADRs
- Comments, docstrings, module overviews
- Commit subjects/bodies and PR titles/descriptions
- Product help, operator manuals, in-app help, API narrative docs
- Any technical prose **in a repository** unless the user asks for another style

## When NOT to use

- Emails, Slack/Teams, stakeholder narratives for non-engineers (prefer **writing-clarity-and-grace**)
- Blog posts, marketing, landing pages, announcements, sales/support macros
- Creative or brand-voice copy
- Small local edits where matching **existing surrounding style** matters more than a full STE rewrite

If the task is external people-facing communication, load **writing-clarity-and-grace** instead.

## Default if unsure

- Working in a **repo** on docs/code prose → use this skill  
- **Outside** a project or clearly external audience → use writing-clarity-and-grace  
- Still unsure → ask one short question

## Intensity by genre

| Genre | Intensity |
| --- | --- |
| Procedures, checklists, install steps, operator actions | **Strict** STE-inspired |
| Architecture rationale, tradeoffs, design discussion | **Looser** — allow longer sentences when needed for nuance |
| Commit / PR prose | **Light** — short imperative subject; clear body; do not force textbook STE |
| Small fix to existing text | **Minimal** — change only what was asked; match neighbors |

## Hard rules

1. **One main idea per sentence.** Prefer short sentences: about 20 words or fewer for steps/instructions, about 25 or fewer for descriptive prose. Split stacked clauses.
2. **Put the actor and action early.** Prefer active voice. Use imperative for steps (“Click Save.”).
3. **Same meaning → same words.** Do not switch synonyms for the same technical action or object in one doc (*start* vs *launch* vs *initiate*).
4. **Prefer concrete verbs.** Avoid vague fillers: *ensure, utilize, facilitate, leverage, perform, handle* when a precise verb exists.
5. **Avoid noun stacks.** Cap stacked nouns before a head noun at three; prefer “configuration of the server” or “server configuration” over longer chains that hide the head noun.
6. **Make pronouns clear.** Replace ambiguous *it / this / they* with the noun when needed.
7. **Limit jargon.** If a term is required, define it once, then reuse the same term.
8. **Do not rewrite protected tokens:** code identifiers, APIs, file paths, commands, error strings, brand names, issue IDs, URLs.
9. **Lists for procedures.** Numbered steps for sequences; bullets for unordered facts.
10. **Warnings first** when safety or data loss matters.
11. **Control tense.** Imperative for steps (“Open the file.”). Simple present for states and behavior (“The service returns 404.”). Simple past for completed events. Avoid future “will” and progressive “-ing” forms in procedures.
12. **Do not strip sentences bare.** Cutting articles, verbs, or subjects to save words adds ambiguity, not clarity.
13. **Keep paragraphs short.** About six sentences per paragraph, one topic each. Start a new paragraph when the topic shifts.

## Soft rules (prefer, do not over-apply)

- Prefer positive form (“Enable X”) over multiple negatives when clear
- Prefer “must / must not” for requirements; avoid decorative modal stacks
- Prefer articles and full words in docs; abbreviations only after definition (except ubiquitous ones: API, URL, HTTP, JSON, CLI)

## Revise checklist

Before finishing, scan for:

- [ ] Multi-clause sentences that can split
- [ ] Passive constructions that hide the actor without a good reason
- [ ] Synonym churn for the same concept
- [ ] Vague verbs (*ensure*, *utilize*, *facilitate*)
- [ ] Ambiguous pronouns
- [ ] Accidental renames of code tokens or product names
- [ ] Full-document rewrite when only a small edit was requested

## Before / after examples

### Procedure

**Before:**  
In order to ensure that the service is properly configured, the environment variables should be set by the user prior to the application being started.

**After:**  
Set the environment variables before you start the application.

### Doc overview

**Before:**  
This module is responsible for the facilitation of connection management and performs handling of retries in the event that network failures are encountered.

**After:**  
This module manages connections. It retries the request when a network failure occurs.

### Commit (light STE)

**Before:**  
Some fixes and improvements around the way we were doing stuff with auth tokens and also cleanup

**After:**  
Fix auth token refresh and remove unused helpers

Body (optional):  
Refresh tokens before expiry. Delete unused auth helpers in `src/auth`.

## Small-edit rule

If the user asks to fix one sentence, add one paragraph, or match existing docs:

- **Do not** rewrite the whole file into STE
- Change only the requested span unless inconsistency would confuse readers

## Optional depth

For denser rules and more examples, open:

- `references/rules-cheatsheet.md`
- `references/examples.md`

Only open these when drafting long docs or when the first pass is weak.

## What not to claim

- Do **not** say the text is “ASD-STE100 compliant” unless the user has a full STE process and dictionary outside this skill.
- Say “STE-inspired” or “simplified technical English principles” if you must label the style.
