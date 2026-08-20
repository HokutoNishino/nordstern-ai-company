# CEO Decision

Date: 2026-08-17  
Decision ID: NS-2026-011  
Related: NS-2026-005, NS-2026-007, NS-2026-008, NS-2026-009
Status: Superseded in part by NS-2026-012 for retention of the standalone source

## Decision

**GO — selectively integrate the useful `Note-idea` knowledge into the Nordstern workspace without moving or deleting the original folder.**

The legacy `Docs/` and `Articles/` trees are copied to `company/ventures/note/archive/note-idea/`. The duplicate `skills/` tree is excluded because all ten skill directories are identical to the active global installations.

## Why

- The source is small: 132 KB and 27 files（20 duplicate Skill files and 7 knowledge/article files）.
- Local reference paths reduce repeated cross-workspace discovery and permission friction.
- Copying identical skills would add search noise and create two update locations.
- The legacy SME strategy conflicts with the current beginner-oriented audience if treated as active context, so it belongs in a clearly marked archive.
- File presence alone does not consume model tokens; the lean context index is the mechanism that reduces unnecessary reads.

## Constraints

- No exact speed or token saving is claimed without measured before/after evidence.
- The standalone source remains recoverable and unchanged.
- The archive is read-only historical context by convention, not an active publishing queue.
- Current decisions and product files remain authoritative.

## Success criteria

- Imported `Docs/` and `Articles/` match the source byte-for-byte.
- Future Note continuations begin with the lean context index and current handoff.
- No duplicate workspace copies of the active Note skills exist.
