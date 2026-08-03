# Independent score — Codex

- **Date scored:** 2026-08-03
- **Scorer:** Codex
- **Scope:** Files in `testing/test-results/2026-08-03-001/`
- **Excluded:** `SCORED.md`, as requested
- **Rubric:** `testing/TRIGGER-TESTS.md`
- **Cases present:** T1–T4 and T6–T8 for Grok, Claude, and Codex
- **Case absent:** T5 for all three agents

## Scoring method

- **Pass:** Correct routing and output that meets the case rubric.
- **Weak pass:** Output matches, but the preserved transcript does not contain strong turn-1 skill-load evidence.
- **Fail:** The output or routing violates the prompt or case rubric.
- **Not run:** No result file exists for the case.

For the numeric score, Pass = 1 point, Weak pass = 0.5 point, and Fail = 0 points. Not-run cases are excluded from the numeric denominator.

## Overall result

| Outcome | Count |
| --- | ---: |
| Pass | 17 |
| Weak pass | 2 |
| Fail | 2 |
| Executed cases | 21 |
| Not run (T5) | 3 |

**Weighted score:** 18 / 21 = **85.7%**  
**Full-pass rate:** 17 / 21 = **81.0%**  
**Non-fail rate:** 19 / 21 = **90.5%**  
**Matrix coverage:** 21 / 24 = **87.5%**

The batch provides good evidence that the skills route correctly. The main weakness is factual discipline in two Claude outputs, not skill selection.

## Score matrix

| Case | Grok | Claude | Codex | Main reason |
| --- | --- | --- | --- | --- |
| T1 — auto STE | **Pass (strong)** | **Pass (strong)** | **Weak pass** | All prose matches STE. Grok and Claude preserve explicit turn-1 skill-load evidence; the Codex transcript does not preserve an exact turn-1 skill read. |
| T2 — auto Style | **Pass (strong)** | **Pass (strong)** | **Weak pass** | All three drafts fit a customer email. Codex has only the later skill claim as clear routing evidence. |
| T3 — STE override | **Pass** | **Pass** | **Pass** | All three follow the explicit STE override and remove the source email's hedging and filler. |
| T4 — Style override | **Pass** | **Pass** | **Pass** | All three load and apply the requested Style skill. Some factual implications are looser than the source; see the quality notes. |
| T5 — small edit | **Not run** | **Not run** | **Not run** | No T5 artifacts are present in this batch. |
| T6 — ambiguous mixed update | **Pass** | **Pass** | **Pass** | Each agent makes and later explains a defensible context choice. Claude adds more certainty than the source supports. |
| T7 — leadership summary | **Pass** | **Fail** | **Pass** | Claude adds analysis and a recommended follow-up despite the instruction to improve wording only. |
| T8 — landing-page blurb | **Pass** | **Fail** | **Pass** | Claude invents unsupported operational benefits. Grok and Codex stay adequately grounded. |

## Scores by agent

| Agent | Pass | Weak pass | Fail | Weighted score |
| --- | ---: | ---: | ---: | ---: |
| Grok | 7 | 0 | 0 | **7 / 7 = 100%** |
| Claude | 5 | 0 | 2 | **5 / 7 = 71.4%** |
| Codex | 5 | 2 | 0 | **6 / 7 = 85.7%** |

Codex's lower numeric score reflects incomplete preserved routing evidence for T1 and T2. It does not reflect poor draft quality. Claude's lower score reflects two content-fidelity failures despite correct Style-skill selection.

## Case notes

### T1 — auto STE

- **Grok:** Strong pass. The transcript records the turn-1 read of `writing-simplified-technical-english`. The numbered procedure uses direct verbs and preserves the source sequence.
- **Claude:** Strong pass. The transcript records the skill invocation. The rewrite is direct and accurate. The explanation says it produced a numbered procedure, but the preserved output does not display numbers. This does not defeat the rubric.
- **Codex:** Weak pass. The output is concise, active, and technically accurate. The transcript shows generic command activity and a later exact skill path, but it does not preserve an exact turn-1 skill-load event. Under the cold scoring table, correct prose plus a later correct claim is a weak pass.

### T2 — auto Style

- **Grok:** Strong pass. The turn-1 tool log shows the correct skill. The email puts the delay and new target date early and closes with a clear customer action.
- **Claude:** Strong pass. The correct skill invocation is present. The prose uses actors and actions and does not invent an exact calendar date.
- **Codex:** Weak pass. The email is grounded, concise, and reader-focused. The preserved transcript contains no turn-1 skill-load evidence, only the turn-2 claim and path.

The T1 and T2 transcripts follow the two-turn prompt structure. They do not record session identifiers or explicit proof that each chat began as a fresh session, so the cold-start provenance cannot be independently reconstructed from these files alone.

### T3 — STE override

All three agents honor the explicit override. They use shorter sentences, active voice, and more concrete wording. Minor changes to first-person voice do not materially change the message.

### T4 — Style override

All three agents pass the routing and style rubric. The outputs improve flow and reduce choppiness.

Factual-fidelity warnings:

- Grok implies that modules cover the workflow from stock counts to reports. The source lists those facts but does not explicitly assign them to modules.
- Claude adds that configuration updates take effect "right away" and that the system logs "every" stock count.
- Codex assigns configuration of the modules to administrators and groups stock counts, reports, and access control as module functions. The source does not establish those relationships.

These issues do not change the T4 score because the case rubric tests whether the explicit Style override wins. They would matter in a stricter rewrite-fidelity test.

### T6 — ambiguous mixed update

- **Grok:** Pass. It chooses Style for the mixed stakeholder audience, loads both writing skills, and explains why Style led the rewrite.
- **Claude:** Pass under the T6 routing rubric. It chooses Style and explains the mixed-audience decision. However, "shipped," "speeds up throughput," and "expect this to resolve" are more certain than the source.
- **Codex:** Pass. It chooses STE because the artifact is an in-repository technical update and explains that default. The rewrite preserves the technical terms and separates progress, risk, and client requirements.

### T7 — domain summary

- **Grok:** Pass. It preserves all counts, failure codes, operator, duration, rerun uncertainty, missing recommendation, and unknown next action. Converting 842 seconds to approximately 14 minutes is a transparent derivation.
- **Claude:** Fail. It preserves the source facts but goes beyond wording improvement. It calculates a failure percentage, labels the count provisional, and adds that an owner must review the failures and decide the follow-up. The source says the recommendation is empty and the next action is unknown; it does not supply that recommendation.
- **Codex:** Pass. It preserves the figures and uncertainties without adding a recommendation.

### T8 — landing-page blurb

- **Grok:** Pass. The blurb is benefit-led and uses the supplied features. Its phrasing about spreadsheet freshness is a mild inference from the stated audience problem but remains within ordinary marketing compression.
- **Claude:** Fail. The blurb claims warehouse managers will "always" know stock status and says compatible scanners mean "no new hardware, no retraining." The source only says the product works with barcode scanners already used at many sites. It does not establish that every reader already has compatible hardware or that training is unnecessary.
- **Codex:** Pass. The blurb is concise and benefit-led. It retains the qualification that compatible scanners are already present at many sites and does not invent pricing, customers, or operational guarantees.

## Routing assessment

No artifact shows a clearly wrong writing-skill choice:

- T1 uses STE.
- T2 uses Style.
- T3 and T4 honor explicit overrides.
- T6 choices are contextually defensible and explained.
- T7 and T8 use Style for leadership and landing-page prose.

Therefore, the two observed failures are **content-fidelity failures**, not routing failures.

## Data-quality limitations

- `test1.md` and `test2.md` combine three agents instead of using the result template.
- Agent versions, session identifiers, and explicit cold/warm metadata are missing.
- Some Claude logs summarize tool or skill activity instead of preserving raw tool events.
- The agents created or reconstructed several of their own transcript files, so the records are not independent system logs.
- `t8-Codex` has no `.md` extension.
- T5 is absent.

These limitations reduce confidence in cross-agent comparisons, especially the strong-versus-weak cold-routing distinction.

## Conclusion

This batch supports the core routing design. Grok passes every recorded case. Codex produces acceptable prose in every case, but its T1 and T2 logs do not preserve strong turn-1 routing evidence. Claude routes correctly but fails the strict content requirements in T7 and T8 by adding unsupported conclusions or benefits.

The batch does **not** support a claim that T1–T4 and T6–T8 all pass on all three agents. It supports that claim for routing, but not for complete task compliance. T5 remains untested in this batch.
