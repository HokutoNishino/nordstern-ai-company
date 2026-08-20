# Workspace Recovery

This directory preserves the verified pre-migration state for the 2026-08-17 multi-venture reorganization.

## Artifacts

- `2026-08-17-pre-multi-venture-workspace.tar.gz` — pre-migration `company/`, `AGENTS.md`, `START_HERE.md`, and the root business launch plan.
- `2026-08-17-pre-migration-sha256.txt` — SHA-256 inventory for the 52 files present before migration.
- `2026-08-17-post-migration-sha256.txt` — SHA-256 inventory for the completed structure, excluding only itself.

Archive SHA-256: `a7e095d1323867f2708d18008f00f01a57936298839f44439e3d5f6c06802be5`  
Archive size: 6.8 MB

## Verified workspace-external backup

Current post-migration backup: `/Users/hokuto/Desktop/nordstern/backups/nordstern-ai-company-v0.1-2026-08-17-post-migration`  
Size at verification: 14 MB  
Manifest entries verified: 65

The external copy's post-migration manifest passed in place. It was then copied from the backup location into a new `/private/tmp` restore-test directory, where the same 65 entries passed again. This protects against accidental deletion or corruption of the active workspace directory.

The backup is outside the workspace but remains on the same Mac. It is not protection against whole-device or disk failure; an off-device or remote backup remains future resilience work and must not be claimed as complete disaster recovery.

## Verification performed

- Archive listing completed successfully.
- The archive was extracted into a new `/private/tmp` directory, never over the live workspace.
- Extracted `company/`, `AGENTS.md`, `START_HERE.md`, and the embedded checksum manifest matched the backup source.
- The Japanese launch-plan filename was Unicode-normalized by extraction, but its SHA-256 remained `b1e4bafd08dad1e113cbf8de673ce80105b3fd0ecb22bf3b9ac26418c2e78761` and its contents matched.
- Note's six PNG assets retained their recorded SHA-256 values after migration.

## Safe recovery procedure

Do not copy or extract a backup over the live workspace.

Preferred current-state verification:

```bash
recovery_test_dir=$(mktemp -d /private/tmp/nordstern-external-recovery.XXXXXX)
cp -a /Users/hokuto/Desktop/nordstern/backups/nordstern-ai-company-v0.1-2026-08-17-post-migration/. "$recovery_test_dir"/
cd "$recovery_test_dir"
shasum -a 256 --check company/core/recovery/2026-08-17-post-migration-sha256.txt
```

Pre-migration archive inspection:

```bash
recovery_test_dir=$(mktemp -d /private/tmp/nordstern-recovery.XXXXXX)
tar -tzf company/core/recovery/2026-08-17-pre-multi-venture-workspace.tar.gz
tar -xzf company/core/recovery/2026-08-17-pre-multi-venture-workspace.tar.gz -C "$recovery_test_dir"
```

Inspect the extracted copy and compare it with the checksum manifest. Restoring files into the live workspace is a separate overwrite operation and requires explicit founder approval plus a file-by-file restoration plan.

Keep the pre-migration recovery package until a stronger off-device or version-controlled baseline exists and the founder explicitly authorizes its removal. Recovery data is not normal business context; do not load or publish it during routine work.
