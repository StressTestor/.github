# Output schema

One format for every agent. The point: any output from any agent can be skimmed in under thirty seconds, and outputs from different agents can sit next to each other without translation.

## The block

```
agent: <name>
run: <UTC timestamp> | <scheduled | triggered: reason | on-demand>
verdict: <one line: act now / worth reading / nothing needs you>

items (cap per agent file):
1. <the claim or finding, one line> [solid | directional | vibes]
   why now: <one line, what this changes for Joe today>
   receipts: <link> · <link>
   age: <how old the newest evidence is>
   next move: <one concrete action, or "none, awareness only">

killed: <N items found but dropped below the evidence bar, one phrase each or just the count>
```

## Field rules

verdict
: The whole run compressed to one line. "act now" means a window is closing. "worth reading" means value with no clock. "nothing needs you" ends the output there, items section omitted.

items
: Ordered by value to Joe, not by recency. Hard cap set in each agent file. An agent that pads to its cap is malfunctioning.

confidence tag
: Mandatory on every item, per the shared vocabulary. An untagged item is a bug.

why now
: Must answer what changes for Joe, not why the topic is interesting. If the honest answer is nothing, the item does not belong in the output.

receipts
: Direct links to posts, pages, or docs. Solid items need the count required by the agent's evidence standard (minimum two independent sources unless the agent file says otherwise). Screenshots referenced in a post are evidence of a claim existing, not of the claim being true.

age
: Newest evidence timestamp, stated plainly ("40 min", "2 days"). Presenting stale as fresh is a firing offense for an agent whose value is timing.

next move
: One action, concrete enough to start ("draft a prompt for dimension X", "read this writeup", "no action"). Never a list.

killed
: The count of findings that failed the evidence bar, so Joe can see the filter working. A run with zero kills and a full item list deserves suspicion.

## Empty runs

```
agent: <name>
run: <timestamp> | scheduled
verdict: nothing needs you
```

Three lines. Done. No summary of what was searched, no consolation items.

## Escalations

Out-of-schedule output is allowed only for conditions listed in the agent's file under triggers, and must open with `verdict: act now` plus the closing-window estimate. An escalation that could have waited for the scheduled run counts against the agent's noise budget.
