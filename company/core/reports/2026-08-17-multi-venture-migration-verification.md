# Multi-Venture Workspace Migration Verification

Date: 2026-08-17  
Decision: NS-2026-013  
Status: Complete; independent QA PASS

## Result

Nordstern's durable memory was separated into company-wide `core/` material and self-contained `ventures/note/` and `ventures/client-services/` workspaces. Backlog hypotheses remain in `company/portfolio.md` without speculative directories.

## Migration controls

- A pre-migration copy was created before any move.
- All previous files were mapped into the new structure; the original company file count was 49, plus the root launch-plan file moved into `core/strategy/`.
- Six Note PNG assets match their pre-migration SHA-256 values and the hashes recorded in their production records.
- All concrete workspace-local paths recorded in Markdown resolve; only documented `<venture-id>` placeholders are intentionally abstract.
- No active-document references to the retired top-level brief, report, decision, product, or archive paths remain. The pre-migration checksum inventory intentionally records the historical paths for recovery.
- CEO decision IDs are globally unique through NS-2026-013.
- The pre-migration archive was extracted into a separate temporary directory and content-verified without overwriting the workspace.
- A 14 MB post-migration backup was created outside the active workspace at `/Users/hokuto/Desktop/nordstern/backups/nordstern-ai-company-v0.1-2026-08-17-post-migration`; all 65 manifest entries passed there.
- That external copy was copied into a new temporary restore-test directory and all 65 entries passed again. It protects against active-workspace deletion or corruption, but not whole-Mac or disk failure.

## QA remediation

Initial independent QA returned PASS WITH CONDITIONS. It found that the combined compliance/prospect register and NS-2026-001 were too venture-specific for `core/`, and that recovery evidence was incomplete.

- The prospect register and NS-2026-001 were moved to `ventures/client-services/`.
- Cross-venture competition, employer-data, resource-use, IP clarification, and stop rules were extracted into `core/briefs/2026-08-17-founder-compliance-boundary.md`.
- A durable pre-migration archive, pre/post checksum inventories, non-overwriting recovery procedure, and extraction test were added under `core/recovery/`.
- A verified workspace-external current-state backup and restore-copy test were completed. Same-device disaster recovery remains explicitly out of scope rather than being claimed as solved.

## Final independent QA

Final result: **PASS**, confidence high. No major or high-risk finding remains. QA independently confirmed venture classification, retired-path removal, Note continuity, the 65-entry external-backup checksum verification, and the restore-copy verification.

Residual limitation: the external backup is on the same Mac and does not protect against whole-device or disk failure. This limitation is documented and does not block the completed workspace reorganization; off-device backup remains future resilience work.
