# Codex Performance and Usage Policy

Saved: 2026-08-17  
Revised: 2026-08-18 under NS-2026-015  
Status: Active for future Nordstern sessions

## Objective

Reduce response latency and slow the depletion of Codex usage while preserving enough quality for Nordstern's routine business and content work.

## Evidence-based diagnosis

- The project overrode the personal default and ran the parent on `gpt-5.6` with `high` reasoning.
- The project allowed five concurrent subagents, and the previous workflow routinely requested all five departments.
- Three specialist definitions also used `gpt-5.6` with `high` reasoning.
- Persistent Fast mode was not selected in the inspected personal or project settings. The current app session's temporary toggle cannot be proven from files alone.
- The active conversation already contains substantial history. A configuration edit cannot remove tokens already present in that thread.

## Active changes

- Parent default: `gpt-5.6-terra`, medium reasoning, low verbosity.
- Specialist defaults: Terra with low or medium reasoning and low verbosity.
- Maximum concurrent subagents: two.
- Project Fast mode: disabled; service tier remains default.
- Delegation: zero to two relevant departments by default, rather than all departments.
- QA: once per meaningful implementation batch; not for trivial edits.
- Specialist reports: concise by default.

## Model routing v2

| Work shape | Default | Typical Nordstern work |
|---|---|---|
| Mechanical, bounded, many candidates | Luna / low | metadata extraction, formatting, status tables, CTA/hashtag candidates, checklist normalization |
| Light judgment | Terra / low | small rewrites, tone adjustment, short summaries, routine marketing review |
| Normal professional work | Terra / medium | parent synthesis, article planning/drafting, research synthesis, implementation, standard QA |
| Material complexity or consequence | Sol / high | production-grade architecture, difficult security/privacy reasoning, conflicting evidence, high-stakes release dispute |

Sol/high is pre-authorized by NS-2026-015 only for one bounded task at a time. Before use, the parent states the material complexity/risk and why Terra/medium is insufficient, then records the use in the measurement log. If the test is not met, use Terra/medium. `xhigh` is not a normal tier and requires separate founder approval after a representative Sol/high attempt shows a concrete quality gap, or for an unusually hard high-consequence task. Any model at `max` also requires separate founder approval.

Department defaults remain planner/developer/qa = Terra/medium, marketer = Terra/low, and parent = Terra/medium. Sales moves to Luna/low for candidate generation and routine pipeline wording; evidence-heavy or consequential sales work is explicitly promoted to Terra/low or medium.

## Quality escalation rule

Use Sol/high only for a bounded task where material legal, security, financial, architectural, or release risk justifies it. State why Terra/medium is insufficient before escalation, allow only one Sol task at a time, and record it. This is a quality exception, not the normal operating mode.

## Expected effect and validation

The direction of effect is lower latency and lower usage than the former Sol/high plus five-agent pattern. No exact percentage is claimed because account-plan conditions, task complexity, caching, tool calls, and current conversation size affect consumption.

Validate over the next three comparable sessions by recording:

| Date | Task | Start remaining usage | End remaining usage | Subagents | Model/effort override | Fast | Notes |
|---|---|---:|---:|---:|---|---|---|
| | | | | | | Off | |

Read the remaining-usage figures from the Codex UI. They are not available from this workspace configuration.

## Session guidance

Start the next task in a fresh thread to drop the current thread's accumulated context, then enter `続きから`. The Note handoff contains the exact resume point, so project history does not need to be copied into the prompt.

For Note work, follow `company/ventures/note/product/note-production-workflow-v0.1.md`. Measure time, model/effort, subagent count, correction rounds, and whether a quality retry was required. API list prices describe relative model tiers but do not prove the user's Codex plan consumption; use the Codex UI's remaining-usage figures for the actual three-session comparison.
