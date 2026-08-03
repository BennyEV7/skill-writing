# Clarity and grace: revision cheatsheet

Use when a draft feels muddy. Diagnose first; then revise.

## Diagnosis prompts

1. Who is the character? Is that character the subject?
2. What is the action? Is it a clear verb?
3. Does each sentence start with something the reader already knows?
4. Does each sentence end on the news or stress?
5. Can any sentence lose 20% of its words without losing meaning?
6. Where is the main point? early enough?
7. What must the reader do after reading?

## Common rewrites

| Pattern | Move |
| --- | --- |
| “A decision was made to…” | “We decided to…” |
| “The implementation of X” | “When we implement X…” / “Implementing X…” |
| “It is important to note that” | Delete; state the note |
| “In order to” | “To” |
| “Due to the fact that” | “Because” |
| “There are many reasons why” | State the reasons; drop the throat-clearing |
| “Going forward” | Delete or name the date/plan |
| “Reach out” | “Email me” / “Reply with…” |

## Channel lengths (defaults)

| Channel | Default shape |
| --- | --- |
| Slack/Teams | 2-6 short sentences; bullets if >3 items |
| Email | Greeting optional; point in first screen; clear ask |
| Stakeholder update | Done / Next / Risk (or Ask) |
| Blog intro | Hook + promise + roadmap in ~1 short section |
| Landing section | Headline benefit + 1–3 proofs + CTA |
| Support | Thanks/ack + answer + next step |

## Tone dials

- **More formal:** full sentences, fewer contractions, titles/roles clear  
- **More warm:** one human acknowledgment, then substance  
- **More urgent:** deadline and consequence early; still polite  
- **More persuasive:** concrete outcome, proof, single CTA  

## Avoid

- Fake urgency and empty superlatives without evidence  
- Explaining your whole process when the reader needs a decision  
- Softening bad news until the point disappears (be clear, then kind)  
- Cutting every "There is / There are" on sight — it's a legitimate way to launch a new topic before making it next sentence's subject ("There are two blockers left. The first is...")

## Concision, extended

| Pattern | Move |
| --- | --- |
| "large in size", "red in color", "the field of medicine" | Drop the redundant category: "large", "red", "medicine" |
| "the reason is because" | "because" |
| "not unlikely", "not infrequently" | "likely", "often" (flip double negatives to a plain affirmative) |
| "at this point in time" | "now" |
| "in the event that" | "if" |
| "a total of 12 servers" | "12 servers" |

## Prepositional-phrase pileups

Stacked "of the / in the / for the" chains are a distinct concision problem from nominalizations — the fix is usually to turn one of the nouns back into a verb, not just trim words.

| Before | After |
| --- | --- |
| "the reduction of the rate of increase in the cost of the project" | "the project's costs are rising more slowly" |
| "the analysis of the results of the review of the proposal" | "analyzing the proposal review's results" |
| "a delay in the delivery of the report on the status of the migration" | "the migration status report is delayed" |

## Emphasis devices

| Device | Example |
| --- | --- |
| It-cleft | "It was the payment API that broke, not the frontend." |
| What-cleft | "What changed is the retry limit, not the timeout." |
| Resumptive modifier (restate a key word, then extend it) | "We shipped the export early, an export that took three sprints to get right." |
| Summative modifier (sum up the clause just stated, then comment on it) | "The team hit every deadline this quarter, a streak worth protecting." |
| Free modifier (a trailing phrase adding detail without a new sentence) | "We paused the rollout, watching error rates climb past 2%." |

## Correctness: real vs. folklore

| Real errors (fix these) | Folklore (leave alone) |
| --- | --- |
| Subject-verb agreement ("the team are" in American usage) | Split infinitives ("to quickly ship") |
| Dangling/misplaced modifiers | Ending a sentence with a preposition |
| Unclear pronoun reference ("it" with two possible antecedents) | "Which" restricted to nonrestrictive clauses only |
| Comma splices that actually confuse the reader | Starting a sentence with "And" or "But" |

## Elegance

- Parallel items get parallel grammar: "fast, reliable, and easy to use" (not "fast, reliable, and it's easy to use")
- Vary sentence length on purpose: a short sentence after two long ones lands harder
- Avoid elegant variation: if "the API" becomes "the service" becomes "the endpoint" for the same thing, the reader starts hunting for a difference that isn't there — repeat the term instead
