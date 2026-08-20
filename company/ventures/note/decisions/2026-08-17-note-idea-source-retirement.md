# CEO Decision

Date: 2026-08-17  
Decision ID: NS-2026-012  
Related: NS-2026-011

## Decision

**GO — retire the redundant standalone `Note-idea` folder after verified integration.**

The source `/Users/hokuto/Desktop/nordstern/Note-idea` was moved, not permanently erased, to `/Users/hokuto/.Trash/Note-idea-nordstern-2026-08-17` after explicit founder authorization.

## Evidence

- The seven business/article Markdown files under `Docs/` and `Articles/` matched `company/ventures/note/archive/note-idea/` byte-for-byte before retirement.
- The twenty files in the ten legacy Skill directories matched the active installations under `/Users/hokuto/.codex/skills/` byte-for-byte.
- The remaining source-only file was `.DS_Store`, a macOS metadata file with no business content.
- The integrated archive remains available under `company/ventures/note/archive/note-idea/`.

## Why

- The standalone folder no longer contains unique business content or active Skill definitions.
- One authoritative workspace path reduces file discovery, permission friction, search noise, and version-drift risk.
- File location alone does not guarantee lower token use or faster reasoning; the lean context index and targeted reads remain the relevant controls.

## Recovery and authority

- The source remains recoverable from the macOS Trash until the Trash is emptied.
- Emptying the Trash is a separate permanent deletion and is not authorized by this decision.
- `company/ventures/note/archive/note-idea/` is historical reference only. Current Note files under `company/ventures/note/briefs/`, `company/ventures/note/product/`, `company/ventures/note/reports/`, and `company/ventures/note/decisions/` remain authoritative.
