# STE-inspired rules cheatsheet

Use only when you need a denser pass. Core skill rules still apply.

## Sentence design

- Prefer under ~20–25 words when the idea is simple
- One instruction or one claim per sentence in procedures
- Prefer SVO (subject–verb–object) order
- Avoid nested subordinate clauses in steps

## Voice and mood

| Situation | Prefer |
| --- | --- |
| User/operator action | Imperative: “Open the file.” |
| System behavior | Active present: “The service returns 404.” |
| Unknown actor / focus on object | Passive is OK: “The key is stored in…” |

## Terminology consistency

1. Pick one term for each concept on first use
2. Keep that term for the rest of the document
3. Prefer project glossary terms if `AGENTS.md` or docs define them
4. Never “improve” a public API name for style

## Words to question

Replace when a clearer verb exists:

| Weak | Prefer examples |
| --- | --- |
| utilize | use |
| facilitate | help, allow, enable (pick the real meaning) |
| ensure | check, set, require, verify (pick the real action) |
| perform X | do the specific verb (run, send, write) |
| leverage | use |
| handle | process, reject, retry, log (be specific) |
| regarding / in terms of | about / for |
| in order to | to |
| prior to | before |
| a number of | some / N |
| the fact that | (delete; restate) |

## Structure patterns

**Procedure**

```text
## Title
Context in one or two short sentences (optional).

1. Step
2. Step
3. Step

Result: ...
```

**Warning**

```text
WARNING: <risk in one sentence>
Do <safe action>.
Do not <unsafe action>.
```

**Description**

```text
<Component> <verb> <object>.
It <behavior>.
When <condition>, it <result>.
```

## Exceptions (do not over-simplify)

- Legal or regulatory wording the user must keep
- Quoted error messages and logs
- Design tradeoffs that need multi-sentence nuance
- Existing house style that project rules require
