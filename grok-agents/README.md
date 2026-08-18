# Grok agent team

A team of seven Grok agents designed around one person's actual workload: a CLI-agent security stack (Sentinel, Ghost, Seance, Triad, Wraith), adversarial LLM evaluation (PromptPressure), a weekly newsletter about the model ecosystem, an X presence with a codified voice, active bug bounty hunting, and earnings-window trading decisions.

Profile refined against 68 repositories under the StressTestor account. The dominant public work is the agent-security stack, so the team leads with it. Full profile notes are in `PROFILE.md`.

Every agent here passed two filters:

1. It maps to a real recurring need, decision bottleneck, or manual grind found in existing working context.
2. Live X data or Grok itself gives it an advantage a general-purpose assistant does not have.

Agents that failed either filter were cut. The full slate, scores, and cut rationale are in `PROPOSALS.md`.

## The team

| Agent | One line | Cadence |
|---|---|---|
| [Sentinel Signal](agents/sentinel-signal.md) | Tracks new attacks against CLI/AI agents the Sentinel stack should catch, plus agent-security ecosystem moves | Daily |
| [Drift Scout](agents/drift-scout.md) | Turns live jailbreak and red-team chatter into candidate prompts for the PromptPressure eval suite | Daily |
| [Sweep Radar](agents/sweep-radar.md) | Detects model releases and silent behavior changes worth an eval sweep, before official notes | Event-driven |
| [Receipts Desk](agents/receipts-desk.md) | Builds the evidence file for Ghost In The Model Weekly so no load-bearing claim ships as Vibes | Weekly |
| [Reply Window](agents/reply-window.md) | Spots rising threads where a @ThatbV reply lands, with a voice-compliant candidate draft | Continuous, capped |
| [Scope Watch](agents/scope-watch.md) | Tracks new AI-scope bounty programs, scope changes, and writeups worth reading | Twice weekly |
| [Earnings Static](agents/earnings-static.md) | Separates what X actually believes about a watchlist ticker from noise before earnings | Per earnings event |

## How the pieces fit

- `SHARED_CONTEXT.md` holds preferences every agent inherits: confidence vocabulary, voice rules, output discipline, hard prohibitions. Safe to share.
- `PRIVATE_CONTEXT.template.md` is the placeholder file for everything that is not safe to share: watchlists, active bounty targets, posting schedule, current project gaps. Fill it inside Grok only. Never commit the filled version.
- `ROUTER.md` maps request types to agents and defines the hand-off chains between them.
- `OUTPUT_SCHEMA.md` defines the one output block format every agent uses, so results from different agents read the same way and can be skimmed in seconds.
- `agents/` holds one standalone file per agent, each with a complete system prompt ready to paste into a Grok task or project.

## Install

For each agent:

1. Create a Grok task (scheduled agents) or project (on-demand agents).
2. Paste the agent's system prompt from its file, the contents of `SHARED_CONTEXT.md`, and your filled private context.
3. Set the schedule listed in the agent file.
4. Run it manually once and check the output against the agent's quality checklist before trusting the schedule.

## Privacy model

This repo is public. The line between files:

- Public: agent designs, process, evidence standards, the @ThatbV handle, and project names already public on GitHub (Sentinel, Ghost, Seance, Triad, Wraith, PromptPressure, LinkDrift, and the rest).
- Private, never committed: ticker watchlists, position or account data of any kind, bounty program targets, private repos and their contents, alternate handles, posting-hours schedule, the specific threat classes the stack does or does not yet cover, anything about people in your life.

If an agent's output would need private context to make sense, that output stays inside Grok.

## Kill criteria

Every agent carries its own success measure and stop conditions. Two team-wide rules:

- An agent that misses its success bar for four consecutive weeks gets paused, not tuned in place. Diagnose first.
- Earnings Static runs on probation from day one. It has the highest noise risk on the team and the strictest kill clause. See its file.
