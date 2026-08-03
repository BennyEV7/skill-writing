## Grok

## User

Using only the facts in email-briefing.md, draft a customer email about the launch delay.
Show the result in chat only. Do not create, edit, or delete any files.

## Assistant

I'll draft the customer email from `email-briefing.md` only, and apply the clarity-and-grace writing skill for the message.

## Tools

- Read: C:\Users\benev\.grok\skills\writing-clarity-and-grace\SKILL.md
- Read: C:\Users\benev\Code\skills-testing\email-briefing.md

## Assistant

**Subject:** Update: launch moved to next Friday

Hi,

We’re writing with an update on the launch we shared earlier.

During final testing we found a billing edge case. To fix it before go-live, we’re delaying the launch by one week. Our new target date is **next Friday**.

You don’t need to do anything right now. If you have questions, reply to this email and we’ll help.

Thank you for your patience,

[Your name]

## User

Before explaining: did you load or open any skill file for that draft? If yes, name the path or skill id. If no, say "none".
Then briefly say why you wrote it the way you did.
Do not rewrite the draft unless I ask.

## Assistant

**Yes.**  
Path: `C:\Users\benev\.grok\skills\writing-clarity-and-grace\SKILL.md`  
Skill id: `writing-clarity-and-grace`

**Why it was written that way:**  
That skill is for external, people-facing prose (including customer emails). I used its checklist: put the point early, keep real actors and actions in subject/verb form, short paragraphs, stress important news (the new date) at the end of key sentences, stay concise, and close with a clear next step. The facts came only from `email-briefing.md`; the skill shaped wording and structure, not content.


## Claude

Using only the facts in email-briefing.md, draft a customer email about the launch delay.
Show the result in chat only. Do not create, edit, or delete any files.
Globpattern: "**/email-briefing.md"
Found 1 file
Read c:\Users\benev\Code\skills-testing\email-briefing.md
writing-clarity-and-grace skill
Draft based solely on the facts in email-briefing.md:

Subject: Launch Update — One-Week Delay

Hi [Customer Name],

We found a billing edge case during final testing of the upcoming launch. To make sure it's fully resolved before go-live, we're delaying the launch by one week. We now expect to launch next Friday.

There's nothing you need to do — we'll keep you posted as we get closer to the new date. If you have any questions in the meantime, just reply here.

Thanks for your patience.

[Your name]

Nothing was added beyond what's in the briefing file — no customer name, sender name, or specific date were specified there, so I left those as placeholders. Let me know if you'd like a different tone or length.

Before explaining: did you load or open any skill file for that draft? If yes, name the path or skill id. If no, say "none".
Then briefly say why you wrote it the way you did.
Do not rewrite the draft unless I ask.
Yes: skill id writing-clarity-and-grace, base path C:\Users\benev\.claude\skills\writing-clarity-and-grace (loaded its main SKILL.md; I did not open the optional references/ files).

Why I wrote it that way: the skill's checklist calls for putting the real actor in the subject ("We found..." instead of "there has been identification of..."), naming the action instead of hiding it in a noun (decided/delay vs. "a decision has been made"), stating the point early, and cutting hedging/empty-opener language from the source briefing. I also kept it short per the "stakeholder email" intensity guidance (clarity + concision, warm but direct) and left placeholders rather than inventing a customer name, sender name, or exact date since those weren't in the briefing file.

## Codex

Using only the facts in email-briefing.md, draft a customer email about the launch delay.
Show the result in chat only. Do not create, edit, or delete any files.

12:47 AM

Worked for 17s

Subject: Launch delayed by one week
Hello,
During final testing, we identified a billing edge case that must be addressed before launch. As a result, we’re delaying the previously announced launch by one week. Our new target date is next Friday.
No action is required from you at this time. If you have any questions, please let us know.
Thank you for your understanding.

12:48 AM

Before explaining: did you load or open any skill file for that draft? If yes, name the path or skill id. If no, say "none".
Then briefly say why you wrote it the way you did.
Do not rewrite the draft unless I ask.

12:49 AM

Yes: C:\Users\benev\Code\skill-writing\skills\writing-clarity-and-grace\SKILL.md
I used its guidance to make the email direct, concise, professional, and reader-focused. I stated the delay early, explained the billing edge case in plain language, included the new target date, and clarified that customers need not act unless they have questions.

12:49 AM

Approve for me

5.6 SolHigh

Work locallyLocal
