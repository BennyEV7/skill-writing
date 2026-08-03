# skill-writing

Author and maintain **writing skills** for AI agents (Grok, Claude Code, Codex).

**Status:** see [docs/STATUS.md](docs/STATUS.md).

**Private personal project** — not licensed for redistribution or contribution.

## Skills

| Skill | Use for |
| --- | --- |
| [`writing-simplified-technical-english`](skills/writing-simplified-technical-english/) | In-project technical prose: docs, comments, commits/PRs, product/help (STE-inspired principles) |
| [`writing-clarity-and-grace`](skills/writing-clarity-and-grace/) | External communication: email, posts, marketing, support/sales (Style/clarity principles) |

These are **inspired/distilled** guides for agents. They are not full ASD-STE100 compliance tooling and do not reproduce textbook text.

Skill **content** (`SKILL.md` + references) is portable across agents. There is **no installer** in this repo (deliberate: automated install can destroy local skill directories).

## Project docs

| Doc | Purpose |
| --- | --- |
| [docs/CHARTER.md](docs/CHARTER.md) | Why we exist, success criteria, non-goals |
| [docs/PLAN.md](docs/PLAN.md) | Phased roadmap |
| [docs/STATUS.md](docs/STATUS.md) | What’s true right now |
| [docs/DECISIONS.md](docs/DECISIONS.md) | Lasting choices and why |
| [docs/TRIGGER-TESTS.md](docs/TRIGGER-TESTS.md) | Trigger matrix and acceptance criteria |
| [docs/test-results/](docs/test-results/) | Per-run trigger test logs |
| [AGENTS.md](AGENTS.md) | Shared rules for AI coding agents |

## AI agents

This repo uses a **one shared brain** model:

1. **`AGENTS.md`** — full project instructions for all agents  
2. **`CLAUDE.md`** — thin pointer for Claude Code  
3. **`docs/*`** — charter, plan, status, decisions  

Agents: read `AGENTS.md`, then `docs/STATUS.md` and `docs/PLAN.md`, before large work.

## Making skills available to agents

Canonical skills live only under `skills/`.

**Do not** run automated install scripts that overwrite directories under:

- `%USERPROFILE%\.grok\skills\`
- `%USERPROFILE%\.claude\skills\`
- `%USERPROFILE%\.codex\skills\`
- `%USERPROFILE%\.agents\skills\`

If you need a skill visible to an agent, create a **junction or copy yourself**, knowing that:

- A **junction** to this repo’s `skills/<name>` updates live when you edit the repo (commit first if the change is risky).
- A **copy** drifts until you replace it again.

Example (Windows, optional, human-run only):

```powershell
# Inspect first. Do not overwrite a real customized directory.
$src = "C:\Users\benev\Code\skill-writing\skills\writing-simplified-technical-english"
$dst = "$env:USERPROFILE\.grok\skills\writing-simplified-technical-english"
# New-Item -ItemType Junction -Path $dst -Target $src
```

Invoke explicitly with:

- `/writing-simplified-technical-english`
- `/writing-clarity-and-grace`

## Getting started

1. Read `docs/CHARTER.md` and `docs/PLAN.md`.
2. Edit skill content only under `skills/`.
3. Commit meaningful skill changes (this repo is the rollback story).
4. Use [docs/TRIGGER-TESTS.md](docs/TRIGGER-TESTS.md) when checking auto-invocation.

## License / use

Private personal project. **Not licensed** for redistribution, modification by third parties, or contribution.

Skill content is original instruction text. Do not treat skills as official ASD-STE100 materials or as a substitute for *Style: Ten Lessons in Clarity and Grace*.
