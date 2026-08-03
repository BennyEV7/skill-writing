# Charter — skill-writing

**Last updated:** 2026-08-03  
**Status:** Active

## One-liner

Author and maintain global writing skills so AI agents write technical project prose with STE-inspired clarity and external communication with Style/clarity principles.

## Problem

Agents default to uneven, verbose, or inconsistent prose. Inside projects, technical writing benefits from controlled, procedural clarity (ASD-STE100-style practices). Outside projects, people-facing writing needs cohesion, emphasis, and audience fit (principles popularized by *Style: Ten Lessons in Clarity and Grace*). Without shared skills, each session re-invents style rules and multi-agent setups drift.

## Goals

1. Ship two portable skills agents can auto-select by context.
2. Keep one canonical source under `skills/`; make skills available to agents only via **human-supervised** link or copy (no destructive installer).
3. Keep content legally careful: STE-inspired principles, original Style checklists — not proprietary dictionaries or book text.
4. Keep skills lean enough to load and follow.
5. Stay suitable for **private personal use**, not unattended distribution.

## Non-goals (for now)

- Full ASD-STE100 certification or official dictionary distribution
- Reproducing copyrighted textbook content
- Automated grammar/style CI
- Brand-specific voice systems for marketing clients
- Automated multi-agent skill installers (too easy to destroy local skills)
- Public redistribution or contribution packaging

## Users

| Who | Need |
| --- | --- |
| Primary user (repo owner) | Consistent agent writing across tools without re-prompting every session |
| Collaborators / agents | Clear, invokable skills with when/when-not rules |

## Success looks like

- Both skills exist under `skills/`; agent homes use human-supervised junctions or copies (no automated installer).
- Agents default to STE-inspired for in-repo technical prose and Style for external comms (cold auto-invoke measured under `testing/`).
- Project docs no longer show template placeholders.
- Skills state limits clearly (inspired / distilled).
- Trigger tests use neutral fixtures so cold-start routing is not primed by skill-meta text.

## Principles

1. One canonical source; install by link/copy, do not maintain three hand-edited copies.
2. Two skills beat one mega-skill for auto-invocation.
3. Honesty about scope: “inspired by” and “distilled principles,” never false compliance claims.
4. Prefer agent checklists and before/after examples over long essays.
5. User override and project `AGENTS.md` outrank writing skills when they conflict.

## Open questions

- Whether optional example banks need expansion after real use
- Whether a short AGENTS.md snippet should be published for other projects later
- Whether multi-agent T5 (small-edit) still holds after the testing/ move
