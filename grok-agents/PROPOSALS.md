# Proposals and scoring

The full slate considered, scored, and cut down to the shipped team. Scores are 1 to 10. Noise risk is scored so that 10 means lowest risk of producing noise (higher is better on every column, so the total is comparable).

## Scoring table

| Agent | Personal relevance | Grok advantage | Expected value | Frequency | Ease | Low-noise | Total | Verdict |
|---|---|---|---|---|---|---|---|---|
| Drift Scout | 10 | 9 | 9 | 8 | 7 | 6 | 49 | Ship |
| Sweep Radar | 10 | 9 | 9 | 6 | 7 | 8 | 49 | Ship |
| Receipts Desk | 9 | 8 | 9 | 7 | 6 | 8 | 47 | Ship |
| Reply Window | 9 | 10 | 8 | 9 | 6 | 5 | 47 | Ship |
| Scope Watch | 9 | 8 | 8 | 6 | 7 | 7 | 45 | Ship |
| Earnings Static | 7 | 9 | 7 | 5 | 6 | 4 | 38 | Ship on probation |
| Voice Twin (auto-drafter) | 8 | 7 | 6 | 8 | 5 | 3 | 37 | Cut, folded into Reply Window |
| Community Pulse (follower sentiment) | 6 | 8 | 5 | 6 | 6 | 4 | 35 | Cut, overlaps Reply Window |
| Repo Radar (dependency chatter) | 6 | 5 | 5 | 5 | 6 | 6 | 33 | Cut, weak X advantage |
| Ship Announcer (launch-timing bot) | 5 | 6 | 4 | 4 | 6 | 5 | 30 | Cut, thin need |

## Why the shipped six

Drift Scout and Sweep Radar sit at the top because they attack the single most valuable recurring workflow: evaluating LLM behavior. Both have a hard Grok advantage. Jailbreak techniques and silent model regressions surface on X hours to days before they reach papers, changelogs, or aggregators. Nothing without live X access can do this well.

Receipts Desk is the highest-leverage safety net. Joe's own voice filter kills load-bearing Vibes claims before publishing. An agent that pre-builds the evidence file turns that from manual grind into a checklist, and X is where the primary sources (author posts, correction threads, benchmark disputes) actually live.

Reply Window is the cleanest Grok-native play on the board. Reply timing is worth more than reply content, and only live X data knows which thread is rising right now. It absorbs the two cut social agents.

Scope Watch maps to real income. Bounty scope changes and program launches get announced and dissected on X first. The advantage is real but the cadence is lower, so it scores just below the top tier.

## Why the cuts

- Voice Twin was a standalone auto-drafter for X posts. Cut because drafting without timing is low value, and Reply Window already drafts the reply when it flags the window. Merged.
- Community Pulse tracked follower sentiment continuously. Cut because it overlaps Reply Window's monitoring and its output ("people feel X about you") rarely drives an action. High noise, low act rate.
- Repo Radar watched X for chatter about Joe's dependencies. Cut because most dependency signal lives on GitHub and mailing lists, not X. Weak platform advantage, so it fails filter two.
- Ship Announcer tried to time product launches to X attention cycles. Cut because Joe ships on his own cadence and the need is thin. A general assistant handles launch copy fine.

## Probation clause for Earnings Static

It ships because the Grok advantage is genuine (pre-earnings retail and expert sentiment is an X-native signal) and it maps to a real decision Joe makes. It ships on probation because it carries the team's highest noise risk and touches money, where a confident-wrong output is expensive. Its file sets a hard rule: it reads discourse and never recommends a trade, and if its first month of outputs do not measurably sharpen Joe's read versus his own baseline, it is cut, not tuned.
