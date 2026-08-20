# Ventures

Each directory represents one active business or founder-approved discovery track.

## Standard layout

```text
<venture-id>/
  README.md     # status, objective, entry point, constraints
  briefs/       # current context and handoffs
  decisions/    # venture-scoped CEO decisions
  reports/      # research, reviews, and results
  product/      # specifications, implementation, and deliverables
  evidence/     # measurements and validation artifacts, when needed
  archive/      # historical inputs excluded from normal reads
```

Create only the directories a venture needs. Use stable lowercase kebab-case IDs. Use `YYYY-MM-DD-<artifact>.md` for dated records and keep existing CEO decision IDs globally unique.

Copy `_template/README.md` when activating a new venture. Record the venture and its entry point in `company/portfolio.md` in the same change.
