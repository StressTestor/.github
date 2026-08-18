# Router

Which agent handles what, and how they hand off to each other.

## By request type

| You want | Agent | Mode |
|---|---|---|
| "Any new attacks against agents my stack should catch?" | Sentinel Signal | Scheduled daily, or ask on demand |
| "Any new jailbreak techniques worth a prompt?" | Drift Scout | Scheduled daily, or ask on demand |
| "Did model X actually change, or is it vibes?" | Sweep Radar | Event-driven, or ask on demand |
| "Verify the claims in this newsletter draft" | Receipts Desk | Weekly, or paste a draft anytime |
| "Is there a thread I should reply to right now?" | Reply Window | Continuous during posting hours |
| "Any new bounty programs in my scope?" | Scope Watch | Twice weekly, or ask on demand |
| "What does X actually think about $TICKER before earnings?" | Earnings Static | Per earnings event only |

## By trigger source

- New model release detected → Sweep Radar fires first.
- Newsletter draft exists → Receipts Desk.
- A thread is spiking on a topic Joe knows cold → Reply Window.
- Earnings date within 48h for a watchlist ticker → Earnings Static wakes.
- A red-team or jailbreak thread is trending → Drift Scout.
- An attack against a CLI/AI agent, an MCP exploit, or an agent-security tool launch → Sentinel Signal.
- A bounty program posts or changes AI scope → Scope Watch.

## The load-bearing ownership line: jailbreak vs agent-compromise

Sentinel Signal and Drift Scout both react to "a new attack technique appeared on X". They never both keep it. The split follows Joe's two products:

- If the technique makes a **model** misbehave (jailbreak, refusal bypass, alignment evasion) it is a PromptPressure concern → **Drift Scout** owns it, output is a candidate eval prompt.
- If the technique compromises an **agent or its tool-chain** at runtime (injection via tool output, exfil, path traversal, unauthorized tool/shell calls, ASCII smuggling, homoglyph, trojan source, MCP abuse, supply chain) it is a Sentinel concern → **Sentinel Signal** owns it, output is a defense gap.
- A technique that is genuinely both (a jailbreak delivered through a tool-output injection) goes to Sentinel Signal for the delivery vector and is cross-tagged to Drift Scout for the payload, each noting the hand-off in `killed`.

## Hand-off chains

The agents are wired to feed each other. These chains are where the team beats six isolated bots.

1. Release to sweep to receipts.
   Sweep Radar flags a real model change → Joe runs the PromptPressure sweep → Receipts Desk files the numbers as solid evidence for the next newsletter → Reply Window watches for the moment the result is worth posting.

2. Scout to sweep.
   Drift Scout finds a technique that breaks a model in the wild → tags it for Sweep Radar to check whether it reproduces across the sweep rotation, not just the one model.

3. Scope to receipts.
   Scope Watch surfaces a notable bounty writeup → if it bears on a newsletter angle, it flags Receipts Desk rather than duplicating the reading.

4. Signal to scope.
   Sentinel Signal finds a new agent-compromise class getting attention → if a bounty program has that surface in scope, it flags Scope Watch, since the same technique is now both a defense gap and a paid target.

5. Signal to receipts.
   A significant agent-security incident or a competitor's move surfaced by Sentinel Signal is often a newsletter angle → it flags Receipts Desk rather than the reading happening twice.

## Conflict rules

- Two agents surface the same event: the one whose core mission owns it keeps it, the other drops it and notes the overlap in `killed`. Ownership: agent-compromise and agent-security ecosystem is Sentinel Signal, model jailbreak is Drift Scout, model behavior change is Sweep Radar, publishing claim is Receipts Desk, discourse-timing is Reply Window, bounty program is Scope Watch, ticker sentiment is Earnings Static.
- An item needs private context another agent holds: it does not travel. The agent surfaces what it can and names the gap.

## What has no agent, on purpose

- Generic news summary, calendar, email triage, scheduling, "research this topic": handled by Joe's general assistant and the morning brief skill, not Grok. No X-data advantage, so no agent here.
- Trade execution or sizing: no agent, ever. Earnings Static reads discourse and stops.
- Anything that would post to X on Joe's behalf: no agent. Every draft is delivered to Joe, who posts himself.
