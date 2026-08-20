# Start Here — Nordstern AI Company

Open this folder as a trusted Codex project.

## Start a session

1. Read `company/portfolio.md`.
2. Select one venture; do not load unrelated venture histories.
3. Read that venture's `README.md` and its current brief or handoff.
4. State the objective, constraints, and success condition before acting.

Current entry points:

- Note: `company/ventures/note/README.md`
- Client services discovery: `company/ventures/client-services/README.md`
- Company-wide policy or portfolio work: `company/core/README.md`

## Prompt for a new or existing venture

> Act as Nordstern CEO.
>
> Venture: [venture ID, or "new hypothesis"]
> Objective: [business objective]
> Constraints: [budget / time / skills / market]
> Success: [measurable outcome]
>
> Read only the relevant portfolio entry, venture README, and current brief.
> Delegate only to departments whose findings can change this decision, with no more than two running in parallel by default.
> Reconcile conflicts and return:
> 1. GO / MODIFY / NO-GO
> 2. recommended offer
> 3. target customer
> 4. first MVP
> 5. first acquisition experiment
> 6. first sales experiment
> 7. 30-day plan
> 8. KPI
> 9. risks and assumptions
> 10. next executable task
>
> Do not send messages, spend money, deploy, or perform external actions without explicit human approval.

For a new hypothesis, keep it in `company/portfolio.md` until the founder approves active discovery or execution. Then create `company/ventures/<venture-id>/` from the documented venture structure.

## After implementation

Ask:

> Have qa independently review the implementation against the business objective and requirements. Do not let qa edit the code. Return PASS, PASS WITH CONDITIONS, or FAIL, with concrete findings and required fixes.

## CLI inspection

In Codex CLI, use `/agent` to inspect/switch between agent threads while subagents are running.
