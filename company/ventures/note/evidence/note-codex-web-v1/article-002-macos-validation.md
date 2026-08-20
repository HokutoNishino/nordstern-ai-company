# Article 002 — macOS Runtime Validation

Status: `human_operated_run_complete`  
Result: `PASS_WITH_COPY_CORRECTION`

The narrow folder-creation, one-file creation, and final no-change flow passed on the documented Mac. The public memo schema was corrected after the two-chat workflow made `作成したフォルダ名` ambiguous. Full setup time and clean-user generalizability remain unclaimed.

## Environment

- Run date/time and timezone: 2026-08-17 17:50:34 JST（自動操作の事前試行）
- Reviewer: Codex parent agent（自動事前確認のみ）
- macOS version/build: 26.6.1 / 25G76
- Hardware architecture: arm64
- ChatGPT app version/build: 26.810.52044 / 6662
- Account management state: unknown（アプリ画面未確認）
- Fresh-user or existing-user environment: unknown（アプリ画面未確認）
- Official download page final URL: https://learn.chatgpt.com/docs/app

Do not record an account email, username-bearing full path, organization name, or unrelated file names.

## Automated attempt — 2026-08-17

- Preflight confirmed that the `codex-practice` target did not exist before the attempt.
- The approved Computer Use interface rejected access to the ChatGPT/Codex app with: `Computer Use is not allowed to use the app 'com.openai.codex' for safety reasons.`
- No ChatGPT/Codex UI action, prompt submission, permission approval, folder creation, or file creation occurred.
- AppleScript, System Events, shell-based UI control, and other bypasses were not used.
- Creating the same artifact outside the desktop-app flow would not validate the article's claimed UI and approval route, so no substitute PASS was recorded.
- Required next evidence: a human-operated run using the exact checklist below.

## Preconditions

- [x] A projectless Codex `New chat` was used（founder-operated; exact Japanese label still to be recorded）.
- [x] The run paused for human approval before creating the target.
- [x] `Full access` was not requested in the reported approval flow.
- [ ] No employer, client, production, or existing-project folder is open.
- [x] No pre-existing `~/codex-practice` target existed in the read-only preflight.

Conflict handling: the first test folder was deleted by the founder to restart the validation. A read-only preflight at 2026-08-17 18:05 JST confirmed that the target was absent before the rerun. No deletion was performed by the agent.

## Run A — Folder planning and creation

Use the exact prompts in `product/note-articles/002-chatgpt-codex-setup.md`.

- Start time: 2026-08-17 17:56 JST（sanitized response received）
- End time: 2026-08-17 18:06:28 JST（clean rerun folder creation）
- Visible route to projectless Codex chat: human-operated run per article instruction; exact UI labels still to be recorded
- Planning response changed local state: no（response explicitly stated no creation or modification）
- Chat used `~/codex-practice` without a username-bearing full path: yes
- Approval dialog exact operation, sanitized: `ChatGPT に codex-practice の内容の編集を許可しますか？ ホームフォルダ直下に、指定された空フォルダを1つだけ作成するためです。`
- Approval dialog requested broader home access: no; the displayed target was `~/codex-practice` only
- Home-folder contents were listed: no（planning response contained none）
- Unrelated files were read or shown: no（planning response contained none）
- `Full access`, administrator access, internet, or third-party access requested: no（planning response explicitly excluded all four）
- Folder creation result: PASS
- Failure or stop details: none on the clean rerun. Read-only verification at 18:06:53 JST confirmed one directory at `~/codex-practice` with zero entries. The first output had been removed by the founder before this rerun.

## Run B — Open local project and create README

- Only the created `codex-practice` folder was selected: yes（planning response confirmed the exact target; recorded only in sanitized form）
- Parent home folder was selected: no
- README planning response changed local state: no（18:09:46 JST read-only check: zero entries; `README.md` absent）
- Planning response displayed a username-bearing full path: yes — privacy correction required before publication; evidence record sanitizes it to `~/codex-practice`
- `実行して` was sent only after exact-plan review: yes; execution message also added the privacy-safe path reminder found necessary during validation
- New files shown in the selected project: `README.md` only; app reported +4 / -0
- Existing files shown as modified or deleted: none reported or found in the selected folder
- README content matched the requested heading and three bullets: yes; 4 lines / 181 bytes
- Extra permission request: none reported after the earlier target-scoped folder permission
- Project-local change-view result: PASS — app showed `README.md` only with review/revert controls; read-only filesystem check matched
- README SHA-256: `8b502426c98acafb48a941b4eb2c4780ad18812de888233115dc1f6f3f510d84`

## Run C — Chat-only result memo

- Memo caused an additional file change: no. Read-only verification on 2026-08-18 found only `README.md`; its modification time remained 2026-08-17 18:10:33 JST.
- Memo matched the project-local change view: yes for OS, date, `README.md`, no existing-file changes, no extra permission, completion status, and exact README content. The folder field said `なし（作成場所: ~/codex-practice）` because the active local-project chat did not create the folder itself.
- Memo included a username-bearing full path: no; it used `~/codex-practice`.
- The reviewer understands that the project-local change view is not whole-device proof: yes.
- Public-copy correction: replace `作成したフォルダ名` with `作業フォルダ名` and a separate fixed-format `作業場所: ~/codex-practice` field.
- Post-memo artifact: one file, 4 lines, 181 bytes, SHA-256 `8b502426c98acafb48a941b4eb2c4780ad18812de888233115dc1f6f3f510d84`.

## Timing and recovery

- Total measured time: approximately 14 minutes from sanitized folder-planning response at 17:56 JST to README completion at 18:10 JST; app download/sign-in time was not measured and no public duration promise is made.
- Observed error: the first test folder was removed by the founder to restart cleanly; the README planning response displayed a username-bearing full path; the final memo's folder-name field was ambiguous across separate chats.
- Tested recovery: founder removed the first test output, reran from an absent target, kept the permission target narrow, added the privacy-safe path reminder, and completed the exact one-file run. The public prompt/schema now encode those corrections.
- Recovery preserved narrow permissions: yes.

## Evidence and verdict

- Sanitized evidence paths: this worksheet; `product/note-articles/002-chatgpt-codex-setup.md`; founder-provided sanitized final memo; read-only verification of `~/codex-practice/README.md`.
- Reviewer notes: validation covers the documented existing-user Apple Silicon Mac and the selected-project/app evidence. It does not prove behavior on every account, fresh installation, Mac model, or elsewhere on the device.
- Final verdict: PASS WITH COPY CORRECTION.
- Publication implication: runtime gate is closed after v0.5.1 prompt/schema correction. Release review and actual Note preview remain required.

PASS requires every safety-critical `yes / no` field to match the expected safe value and no unresolved `unknown` for folder scope, unrelated reads, permission breadth, or changed files.
