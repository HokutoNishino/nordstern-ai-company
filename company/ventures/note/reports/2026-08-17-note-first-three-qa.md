# QA Report — Note Free Articles #1–#3

Date: 2026-08-17  
Decision: NS-2026-008  
Reviewer: `qa` department (`note_series_qa_v2`)  
Final confidence: High

## Scope

- `company/ventures/note/decisions/2026-08-17-note-first-three-and-sequence.md`
- `company/ventures/note/product/note-codex-web-series-v0.3.md`
- `company/ventures/note/product/note-articles/001-introduction.md`
- `company/ventures/note/product/note-articles/002-chatgpt-codex-setup.md`
- `company/ventures/note/product/note-articles/003-git-basics.md`

## Initial decision

**PASS WITH CONDITIONS.** The requested sequence and production-package structure were correct. Article #1 was close to human review. Articles #2 and #3 remained external-release NO-GO pending practical validation.

## Initial high findings

### 1. Service processing versus additional network access

The #2 draft used `外部送信を許可しない` while instructing the reader to send prompts and selected work context to ChatGPT / Codex. This could imply that no content leaves the PC.

Required correction:

- State that submitted prompts and selected context are processed by the service.
- Use only fictional, non-confidential information.
- Distinguish this from Codex-initiated additional internet access or third-party transmission.
- Check account data settings, terms, and organization policy.
- Keep a human approval mode and avoid full access.

### 2. Existing parent Git repository

The #3 draft verified only the folder name before `git init`. A `codex-practice` folder could still be inside an existing parent repository.

Required correction:

- Detect an existing current/parent repository before initialization.
- Stop if a parent path is returned.
- Create a fresh practice folder outside that repository.
- Never delete, move, or reinitialize the existing repository as a workaround.

## Corrections applied

- #2 now states that prompts and selected context are processed by the service, limits exercises to fictional non-confidential data, and distinguishes service processing from agent-initiated additional internet / third-party access.
- #2 now requires review of data settings, terms, organization policy, and permission mode; Full access is excluded.
- #3 carries the same service-processing distinction.
- #3 now runs `git rev-parse --show-toplevel` before `git init`. `not a git repository` is the expected fresh-folder result; a printed path triggers a stop and recreation outside the existing repository.
- Decision NS-2026-008 and series v0.3 now contain both controls.

## Local isolated technical check

Environment: current Mac, Darwin arm64, Git 2.42.0. This was an isolated command check, not a clean-environment or beginner-flow validation.

Observed:

- In a temporary directory outside a repository, `git rev-parse --show-toplevel` exited with `not a git repository`.
- In a harmless test subdirectory under a temporary parent repository, the same command printed the parent path, supporting the intended stop decision.
- In the isolated safe directory, the drafted sequence completed: `git init`, explicit `git add README.md index.html`, repository-local identity, commit, log, disposable edit, diff, `git restore -- index.html`, and final clean status.
- The `git init` output included a default-branch hint with a global-config example. The article now tells the reader that this is not a failure and not to change the global setting in this exercise.

This evidence does not validate the current ChatGPT desktop-app UI, a clean Git installation, Windows behavior, beginner completion, or measured time.

## Final independent re-review

- High finding 1: **Resolved**.
- High finding 2: **Resolved**.
- New blocker/high findings: **None**.
- Document decision: **PASS WITH REQUIRED VALIDATION**.

## Article release decisions

| Article | Document status | External release |
|---:|---|---|
| #1 | PASS WITH HUMAN CHECKS | May be reconsidered after author confirms personal disclosures, voice, title, thumbnail rights, CTA, and final preview |
| #2 | PASS WITH REQUIRED VALIDATION | **NO-GO** until clean macOS and native Windows runs, current UI/source review, QA of the evidence, and human approval |
| #3 | PASS WITH REQUIRED VALIDATION | **NO-GO** until clean macOS and native Windows runs, destructive-step evidence review, QA of the evidence, and human approval |

## Remaining required actions

1. Author approves or edits the #1 personal biography and first-person voice.
2. Validate #2 end to end on clean macOS and native Windows, including account conditions, permission mode, exact UI, changed files, and measured time.
3. Validate #3 end to end on clean macOS and native Windows, including Git absence/install paths, parent-repository detection, explicit staging, local identity fallback, commit, diff, restore, and final state.
4. Save sanitized evidence with OS/app/Git versions and observed errors.
5. Recheck OpenAI claims and links within 48 hours of publication and Git documentation immediately before publication.
6. Run QA again on the practical evidence and final paste-ready copy.
7. Obtain article-level human approval and publish manually. No external publication has been authorized by this report.
