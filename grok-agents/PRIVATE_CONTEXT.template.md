# Private context template

Fill this inside Grok only. The filled version never gets committed, pasted into a public repo, or included in any agent output. This template ships with placeholders so the repo stays clean.

Each agent file lists which of these blocks it needs. Give an agent only its listed blocks, not the whole file.

## Identity

- Alternate X handles that must never be linked to the main account in any output: `[REDACTED_LIST]`
- Accounts to never engage, quote, or amplify (blocklist): `[REDACTED_LIST]`

## Posting (Reply Window)

- Active posting hours, local time: `[e.g. 07:00-09:00, 19:00-23:00 MT]`
- Current follower count and 30-day baseline engagement per reply: `[NUMBERS]`
- Topics currently off-limits or exhausted: `[LIST]`
- Recently used kaomoji (last 10 posts, for the no-repeat rule): `[LIST]`

## Eval work (Drift Scout, Sweep Radar)

- Drift dimensions currently thin on prompts: `[e.g. persona override, tool-call coercion]`
- Models currently in the sweep rotation: `[LIST]`
- Techniques already in the suite (so Scout stops resurfacing them): `[LIST OR LINK TO INDEX]`

## Newsletter (Receipts Desk)

- Issues in the pipeline and their working angles: `[LIST]`
- Angles already covered in the last 8 issues: `[LIST]`

## Bounty (Scope Watch)

- Programs currently active on: `[REDACTED_LIST]`
- Target profile (what a good program looks like right now): `[e.g. LLM integration surface, agent frameworks, paid, managed triage]`
- Programs to ignore: `[REDACTED_LIST]`

## Trading (Earnings Static)

- Current watchlist tickers: `[REDACTED_LIST]`
- Never include in any output: position sizes, account values, order history, broker details.
- Risk posture note for framing only, never for advice: `[e.g. defined-risk options around earnings, no overnight naked positions]`

## Escalation

- What justifies an out-of-schedule alert: `[e.g. new AI-scope bounty program, major model release, active exploit against a tool I use]`
- Quiet hours where nothing interrupts: `[HOURS]`
