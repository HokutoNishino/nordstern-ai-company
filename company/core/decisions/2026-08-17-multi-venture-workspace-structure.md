# CEO Decision

Date: 2026-08-17  
Decision ID: NS-2026-013  
Scope: core

## Decision

**GO — organize Nordstern as a multi-venture workspace.**

Company-wide material lives under `company/core/`. Each active business or approved discovery track lives under `company/ventures/<venture-id>/` and owns its briefs, decisions, reports, product work, evidence, and archive. Unapproved ideas remain in `company/portfolio.md` without speculative directories.

## Why

- The previous shared `briefs/`, `decisions/`, `reports/`, and `product/` directories mixed company policy, client-services discovery, and Note operations.
- Venture isolation reduces irrelevant reads, filename collisions, accidental cross-business assumptions, and unclear ownership.
- A small portfolio registry preserves a company-wide view without requiring every venture's files to be loaded.

## Specialist inputs and reconciliation

- Planning recommended immediate separation into company core and venture workspaces.
- Development recommended a staged migration because path references and the absence of Git increase rollback risk.
- The selected approach uses the core/venture model and completes the small migration now, with a temporary pre-migration copy, full path replacement, content checks, and independent QA before completion.

## Initial classification

- `note`: active venture.
- `client-services`: discovery venture for non-SES contract Web development and small workflow improvement.
- Own apps/platforms and dropshipping: portfolio backlog only.

The founder-wide competition, employer-data, and resource-use boundary is extracted to `company/core/briefs/2026-08-17-founder-compliance-boundary.md`. Prospect registers, contact procedures, market hypotheses, and the first management-meeting business experiment remain under `client-services`.

## Success criteria

- Every current artifact has one authoritative core or venture location.
- All recorded workspace paths resolve after migration.
- Note continuation still starts from one lean context index.
- New ventures have a documented activation gate and standard entry point.
