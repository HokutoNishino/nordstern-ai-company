# Note Codex Web Series v0.3

Date: 2026-08-17  
Status: Adopted; Articles #1 and #2 published, later articles require separate approval  
Decision: NS-2026-008, updated by NS-2026-014  
Updates: `note-codex-web-series-v0.2.md` and the launch path in `note-account-brand-v0.1.md`; copyability rule added by founder request on 2026-08-17; Article #2 narrowed to macOS on 2026-08-17

Where this file and v0.2 differ, this file is authoritative for the free 10-article order, the purpose and completion condition of each article, and the first three production packages. `note-account-brand-v0.1.md` remains authoritative for the account name, profile, audience, positioning, series labels, and news policy. The cadence, pricing hypothesis, paid-product scope, budget, safety controls, evidence requirements, and human approvals in v0.2 remain in force.

## Business objective, constraints, and success

### Objective

Guide a beginner from choosing a first Web artifact to building a small local prototype with AI, while establishing safe information handling, change history, and a publish/no-publish review process.

### Constraints

- No public client work or employer information may be used.
- The free series must not promise income, client acquisition, independence, employment, ranking, traffic, sales, or universal production safety.
- Each article teaches one central issue, produces one small artifact, and points to one next action.
- Product UI, availability, commands, and operating-system steps require current official sources and practical verification.
- External publication, profile changes, spending, and synchronization to `Note-idea` require human approval.

### Definition of success

The first 10 articles form one continuous path:

> choose → prepare → record → back up → understand delivery → learn the page parts → specify → build → review

A reader can stop after any article with a useful small artifact, and can resume from that artifact in the next article.

## Editorial thesis

The free series is not a dictionary of unrelated terms. Every foundational topic is taught in relation to one beginner outcome: creating and eventually publishing a small HP, LP, portfolio, or fictional-service page.

The editorial rhythm is:

- short explanation;
- safe, limited action;
- visible completion check;
- next-article bridge.

Use standard Japanese for instructions and a light Kansai voice for transitions or reassurance. Recommended tone balance: clarity 7, natural Kansai flavor 2, humor 1. Do not force dialect into commands, safety warnings, or error explanations.

## Audience and initial artifact choices

Primary reader: a beginner who wants to use AI to create and publish a first portfolio, fictional-service LP, or small HP/LP.

At the end of #1, the reader chooses one of:

1. 自分のポートフォリオ
2. 架空サービスのLP
3. 自分の事業・店舗・活動を紹介する1ページサイト

The reader writes only:

```text
作りたいもの:
見てほしい人:
伝えたいこと:
```

They should not enter employer, client, customer, confidential, credential, or personal-contact information into the exercise.

## Adopted free 10-article path

| # | Working title | Type | One central issue | Completed artifact | Next bridge |
|---:|---|---|---|---|---|
| 1 | はじめまして、ひつじ先生です。AIとWEBの「なんやねん」を一緒にほどきます | Introduction | Who this account helps and what readers will make | Three-line first-artifact memo | Prepare the AI workspace |
| 2 | CodexとVS Code、結局なんやねん？Macで始める安全なAI開発入門 | Explainer + mini hands-on | Separate conversation/planning from folder-level work and start safely | Empty practice folder, intended `README.md`, environment memo | Put change history around the folder |
| 3 | Gitって何？AIで作ったHPを壊さず育てるための最初の一歩 | Explainer + hands-on | Record, inspect, and deliberately restore a local change | Local repository and first commit | Learn safe remote storage and public/private boundaries |
| 4 | GitHubって何？Gitとの違いと、公開してはいけない情報 | Explainer | Remote collaboration/publication is not the same as local history | Repository-publication plan and secret check | Connect the safe practice repository |
| 5 | GitとGitHubをつないでみよう：保存・push・戻し方の基本 | Hands-on | Back up an explicit local history without exposing unrelated files | Practice GitHub repository, push record, recovery check | Understand how a browser receives a site |
| 6 | HTTP・HTTPS・ドメイン・DNS・サーバーのつながり | Explainer | Map the request path from URL to a delivered page | One-page delivery map | Learn what the delivered page contains |
| 7 | HTML・CSS・JavaScriptは何をしている？ | Explainer + mini hands-on | Separate structure, appearance, and behavior | Minimal local static page | Decide what the actual page should say |
| 8 | Codexに頼む前に作る、1ページHP・LPの設計メモ | Hands-on | Define audience, message, sections, constraints, and non-goals before code | One-page production brief | Give Codex a bounded implementation task |
| 9 | Codexで1ページ試作品を作る：小さく頼んで差分を見る | Hands-on | Build in small reviewed changes | Local one-page prototype and change log | Decide whether it is safe and ready to publish |
| 10 | 公開前チェック：SEO・安全性・アクセシビリティ・性能・戻し方 | Checklist hands-on | Make a transparent Go / No-Go decision | Completed review record and next-fix list | Evaluate need for the paid end-to-end guide |

## Why Git is article #3

HTTP is foundational, but Git must precede meaningful AI-assisted code editing. Articles #7 through #9 will create and change files. Readers therefore need a local history, a way to inspect differences, and a limited recovery exercise before those edits begin. HTTP moves to #6, where it naturally connects GitHub and the local page to later publishing.

## Article #2 scope

### Included

- The practical difference between ChatGPT and Codex for this series.
- Installation/sign-in through official ChatGPT desktop-app guidance for macOS.
- A projectless Codex chat that first plans, then creates one isolated `codex-practice` folder under narrow human approval.
- The reader selects only the created folder as the local project; the reader does not manually create folders/files or enter code/Markdown.
- One constrained local-project task: plan, then create `README.md` only.
- Review of the exact folder target, requested file change, permission scope, and project-local app change display before accepting each action.
- A chat-only environment memo that avoids username-bearing full paths.
- Explicit rules against employer/client folders, credentials, personal data, and unnecessary permissions, plus a clear distinction between service processing of submitted context and agent-initiated additional internet or third-party access.

### Excluded

- Codex CLI as the main route.
- Windows procedures, screenshots, compatibility claims, and support; only an official Windows-guide pointer is included.
- API keys, API billing, or automation.
- Full-access or administrator mode.
- Package installation, agent-initiated additional internet or third-party access, deployment, GitHub, or production code.
- A comparison of every AI product or every ChatGPT feature.

### Completion condition

On macOS, the reader can explain that ChatGPT helps discuss and organize the task, while Codex can act on a narrowly selected work context. Without manually creating a folder/file or typing code, the reader has reviewed and approved one isolated `codex-practice` folder, opened only that folder as the local project, reviewed and approved `README.md` alone, checked the project-local change display, and compared it with a chat-only environment memo. The reader also understands that the app change view does not prove the absence of changes elsewhere on the Mac.

## Article #3 scope

### Included

- Version control as a record of file states over time.
- Git versus GitHub in one paragraph; GitHub work starts in #4.
- `git --version`, `git init`, `git status`, explicit `git add`, first commit, `git log`, `git diff`, and a deliberately limited `git restore` exercise.
- Repository-local identity fallback for the practice repository only.
- Location verification and parent-repository detection before any Git write command.

### Excluded

- `git reset --hard`, force push, rebase, merge-conflict resolution, branching strategy, and team workflows.
- Existing projects, company repositories, client work, and production repositories.
- Bulk staging with `git add .`.
- GitHub account setup or public repository creation.

### Completion condition

The reader first confirms that the practice folder is not inside an existing parent repository. The practice folder then contains an initial commit of the explicitly named practice files. The reader makes one disposable uncommitted change, confirms it with `status` and `diff`, restores only that file after acknowledging data loss, and finishes with a clean status.

## Publication calendar

The target calendar remains conditional on article-level human approval and quality gates.

| Week | Tuesday | Thursday | Friday | Weekend work |
|---|---|---|---|---|
| 1 | #1 | #2 | #3 | #2 published; validate #3 on clean macOS / native Windows; paid-guide specification |
| 2 | #4 | #5 | — | Paid sample implementation |
| 3 | #6 | #7 | #8 | Cross-OS reproduction and corrections |
| 4 | #9 | #10 | — | Independent QA and sale/no-sale decision |

This is a target, not a publishing commitment. If clean-environment validation or correction is incomplete, move the article rather than remove the gate. Do not begin paid sales before all 10 free articles and the paid-product gates are complete.

## Common package requirements

Each production package must contain:

1. Metadata, audience, reader start state, central issue, completed artifact, and non-goals.
2. Recommended title and alternatives.
3. Paste-ready table of contents and body.
4. A 1280 × 670 thumbnail specification; an actual image is optional and requires rights confirmation.
5. Important-claim ledger with source URL, displayed publication/update date or `not displayed`, checked date, and recheck deadline.
6. Afterword decision.
7. Pre-publication review result and prioritized corrections.
8. Human checks, practical-validation evidence, and publication status.
9. Every reader-entered prompt, folder name, command, code sample, configuration, and reusable memo must be placed in its own native Note code block so it can be copied without surrounding prose. Put explanations and warnings outside the block, avoid line numbers or decorative prefixes, and verify the public copy control before publication.

Use only current first-party documentation for OpenAI product behavior and current first-party Git/GitHub documentation for technical behavior wherever available. Avoid screenshots that reveal an account name, file path, organization, client name, notification, token, or personal information.

## Status model for the first three

| Article | Draft status | Publication gate |
|---:|---|---|
| #1 | `human_review_pending` | Biography, `私` voice, title, FDE wording, CTA, and thumbnail v1 are approved; actual Note preview/crop and separate manual-publication approval remain |
| #2 | `published_by_human` | Published and verified 2026-08-18: `https://note.com/witty_ram1894/n/n21310a3790ae` |
| #3 | `validation_required` | Clean macOS and native Windows Git runs; destructive-step warning verified; QA; human approval |

`validation_required` is not a publishable state. Article #2 is already narrowed to macOS under NS-2026-014. For later articles, if one claimed OS cannot be tested, narrow the title and body to the verified OS instead of claiming cross-platform support.

## Measurement

Record only voluntary, non-sensitive feedback:

- selected first artifact;
- reader purpose category;
- OS;
- completed artifact;
- stopping step and sanitized error category;
- request for the next article;
- author production, validation, revision, and support time.

Do not interpret views or likes as proof of purchasing intent or demand in the real-estate, nightlife, or SES markets.

## Human approvals required

- Personal biography and role disclosure in #1.
- Every title, body, thumbnail, CTA, screenshot, and external link.
- macOS / Windows support language.
- New account, subscription, software, hosting, domain, image, or test-device spending.
- Every external note publication, profile update, reader reply, and `Note-idea` synchronization.

## References

Checked on 2026-08-17:

- OpenAI, ChatGPT desktop app: https://learn.chatgpt.com/docs/app
- OpenAI, Codex CLI: https://learn.chatgpt.com/docs/codex/cli
- OpenAI, Windows app: https://learn.chatgpt.com/docs/windows/windows-app
- OpenAI, WSL: https://learn.chatgpt.com/docs/windows/wsl
- OpenAI, Sandboxing: https://learn.chatgpt.com/docs/sandboxing
- Git, About Version Control: https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control.html
- Git, What is Git?: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
- Git, `git-init`: https://git-scm.com/docs/git-init
- Git, `git-status`: https://git-scm.com/docs/git-status
- Git, `git-restore`: https://git-scm.com/docs/git-restore
- GitHub Docs, About Git: https://docs.github.com/en/get-started/using-git/about-git
- note, recommended image sizes: https://www.help-note.com/hc/ja/articles/360000231642-%E7%99%BB%E9%8C%B2%E7%94%BB%E5%83%8F%E3%81%AE%E6%8E%A8%E5%A5%A8%E3%82%B5%E3%82%A4%E3%82%BA%E4%B8%80%E8%A6%A7
- note, heading-image guidance: https://www.help-note.com/hc/ja/articles/900000061623-%E8%A6%8B%E5%87%BA%E3%81%97%E7%94%BB%E5%83%8F%E3%81%AE%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88
