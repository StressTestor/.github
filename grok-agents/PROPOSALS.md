# Proposals and scoring

The full slate considered, scored, and cut down to the shipped team. Scores are 1 to 10. Noise risk is scored so that 10 means lowest risk of producing noise (higher is better on every column, so the total is comparable).

The first pass proposed ten and shipped six, before a scan of all 68 repos. That scan changed the profile: the agent-security stack (Sentinel, Ghost, Seance, Triad, Wraith) is Joe's most active public work, not a side interest. A seventh agent, Sentinel Signal, was added to cover it, and it scores at the top of the team. The revised table:

## Scoring table

| Agent | Personal relevance | Grok advantage | Expected value | Frequency | Ease | Low-noise | Total | Verdict |
|---|---|---|---|---|---|---|---|---|
| Sentinel Signal | 10 | 9 | 10 | 8 | 7 | 6 | 50 | Ship |
| Drift Scout | 10 | 9 | 9 | 8 | 7 | 6 | 49 | Ship |
| Sweep Radar | 10 | 9 | 9 | 6 | 7 | 8 | 49 | Ship |
| Receipts Desk | 9 | 8 | 9 | 7 | 6 | 8 | 47 | Ship |
| Reply Window | 9 | 10 | 8 | 9 | 6 | 5 | 47 | Ship |
| Scope Watch | 9 | 8 | 8 | 6 | 7 | 7 | 45 | Ship |
| Earnings Static | 7 | 9 | 7 | 5 | 6 | 4 | 38 | Ship on probation |
| Ecosystem Gap Scout (build-next radar) | 8 | 7 | 6 | 6 | 5 | 4 | 36 | Cut, folded into Sentinel Signal + Reply Window |
| Voice Twin (auto-drafter) | 8 | 7 | 6 | 8 | 5 | 3 | 37 | Cut, folded into Reply Window |
| Community Pulse (follower sentiment) | 6 | 8 | 5 | 6 | 6 | 4 | 35 | Cut, overlaps Reply Window |
| Repo Radar (dependency chatter) | 6 | 5 | 5 | 5 | 6 | 6 | 33 | Cut, weak X advantage |
| Ship Announcer (launch-timing bot) | 5 | 6 | 4 | 4 | 6 | 5 | 30 | Cut, thin need |

## Why the shipped seven

Sentinel Signal is now the top of the team. A runtime-defense stack for CLI AI agents is only as current as its threat model, and agent-exploitation research (tool-output injection, exfil, MCP abuse, ASCII smuggling) surfaces on X as proof-of-concepts before it reaches CVEs or blogs. Watching that frontier is exactly what decides Sentinel's next detection. The Grok advantage is hard and the value is direct: it maps to Joe's most active public product line.

Drift Scout and Sweep Radar sit just behind because they attack the other core workflow: evaluating LLM behavior. Both have a hard Grok advantage. Jailbreak techniques and silent model regressions surface on X hours to days before they reach papers, changelogs, or aggregators. Nothing without live X access can do this well. Drift Scout and Sentinel Signal share a trigger (a new attack appears) but split cleanly on Joe's two products: model jailbreak versus agent compromise. The `ROUTER.md` ownership line keeps them from doubling up.

Receipts Desk is the highest-leverage safety net. Joe's own voice filter kills load-bearing Vibes claims before publishing. An agent that pre-builds the evidence file turns that from manual grind into a checklist, and X is where the primary sources (author posts, correction threads, benchmark disputes) actually live.

Reply Window is the cleanest Grok-native play on the board. Reply timing is worth more than reply content, and only live X data knows which thread is rising right now. It absorbs the two cut social agents.

Scope Watch maps to real income. Bounty scope changes and program launches get announced and dissected on X first. The advantage is real but the cadence is lower, so it scores just below the top tier.

## Why the cuts

- Ecosystem Gap Scout watched X for unmet needs and complaints in the solo-builder and Claude Code tooling niche, to inform what Joe builds next (he ships small tools fast: batstack, delegate, pr-prism, Agora). Cut as a standalone because its two real signals are already covered: agent-security gaps and competitor moves go to Sentinel Signal, and Reply Window already reads his domains for what the field is reacting to. A separate "what should I build" bot with no product to anchor it drifts into generic trend-watching, which fails filter two. If the product-gap need grows, it becomes a scoped question to Sentinel Signal, not a new agent.
- Voice Twin was a standalone auto-drafter for X posts. Cut because drafting without timing is low value, and Reply Window already drafts the reply when it flags the window. Merged.
- Community Pulse tracked follower sentiment continuously. Cut because it overlaps Reply Window's monitoring and its output ("people feel X about you") rarely drives an action. High noise, low act rate.
- Repo Radar watched X for chatter about Joe's dependencies. Cut because most dependency signal lives on GitHub and mailing lists, not X. Weak platform advantage, so it fails filter two.
- Ship Announcer tried to time product launches to X attention cycles. Cut because Joe ships on his own cadence and the need is thin. A general assistant handles launch copy fine.

## Probation clause for Earnings Static

It ships because the Grok advantage is genuine (pre-earnings retail and expert sentiment is an X-native signal) and it maps to a real decision Joe makes. It ships on probation because it carries the team's highest noise risk and touches money, where a confident-wrong output is expensive. Its file sets a hard rule: it reads discourse and never recommends a trade, and if its first month of outputs do not measurably sharpen Joe's read versus his own baseline, it is cut, not tuned.
