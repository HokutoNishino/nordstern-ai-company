# Note Codex Web Series v0.2

Date: 2026-08-16
Status: Proposed
Decision: NS-2026-006
Integrated legacy reference: `company/ventures/note/archive/note-idea/`  
Former standalone source retired under NS-2026-012; recoverable at: `/Users/hokuto/.Trash/Note-idea-nordstern-2026-08-17` until Trash is emptied

## Series identity

Name: **はじめてのCodex Web制作**

Reader: Web開発経験が浅い小規模事業者、個人事業主、兼任Web担当者。

Outcome: Codexを安全に始め、変更履歴を残し、Web公開の仕組みを理解し、限定された静的事業サイトを自分で作って公開判断できるようになる。

Positioning:

> GitやHTTPを覚えることが目的ではない。
> Codexで作ったサイトを壊さず、安全に公開し、自分で育てるために必要な分だけ学ぶ。

## Editorial rules

- 各無料記事は、一つの疑問、一つの成果物、一つの次行動に限定する。
- 用語の網羅ではなく、最初の有料プロジェクトの前提を順番に解消する。
- 製品・UI・料金・OS依存の操作は公開48時間前に公式情報と検証環境で再確認する。
- Mac/Windowsの共通部分は共通化し、差分だけを各OS記事へ記録する。
- コマンドはコピーだけでなく、実行場所、期待結果、失敗時の戻し方を示す。
- 読者に秘密情報、顧客情報、認証情報をAIや公開リポジトリへ入力させない。
- 公開、販売、価格変更、読者返信は自動化しない。

## Ten free articles

| # | Type | Working title | Reader question | Completed artifact | CTA |
|---:|---|---|---|---|---|
| 1 | 解説・判断 | Codexとは？非エンジニアがHP制作でできること・任せてはいけないこと | AIに何を任せ、何を人が確認するのか | 1ページのサイト目的・対象・非対象メモ | MacまたはWindowsの導入記事へ |
| 2 | OS別ハンズオン | macOSでCodexを始める：安全な練習フォルダで最初の依頼をする | Macでどこから始めるのか | Codexを使える練習フォルダと最初の確認結果 | Windows読者は#3、Mac読者は#4へ |
| 3 | OS別ハンズオン | WindowsでCodexを始める：ネイティブ環境とWSLを迷わず選ぶ | PowerShellとWSLのどちらを使うのか | 選択理由付きの練習環境と最初の確認結果 | #4へ |
| 4 | 解説 | Gitとは？AIが変更したサイトを壊さず戻すための履歴 | なぜ保存だけでは足りないのか | 変更、コミット、復旧の簡易図 | #5へ |
| 5 | 解説 | GitHubとは？Gitとの違い、非公開・公開、秘密情報の基本 | GitHubへ何を置き、何を置かないのか | リポジトリ公開範囲と秘密情報チェック | #6へ |
| 6 | ハンズオン | GitとGitHubの最小実践：最初のコミット、push、元に戻す | 本当に変更を保存・復旧できるか | 練習リポジトリと復旧記録 | #7へ |
| 7 | 解説 | HTTP/HTTPS・ドメイン・DNS・ホスティングとは？サイト公開の地図 | URLを開くと何が起き、誰が何を管理するのか | 公開経路の一枚図 | #8へ |
| 8 | 解説＋小演習 | HTML・CSS・JavaScriptとは？スマホ対応サイトの最低限 | 画面は何でできているのか | ローカルで表示できる1ページ | #9へ |
| 9 | ハンズオン | Codexで1ページの事業サイト試作品を作る：依頼、確認、修正 | Codexへどう仕事を渡すのか | ローカルの試作ページと確認ログ | #10へ |
| 10 | ハンズオン・総点検 | 公開前チェック：SEO・安全性・アクセシビリティ・性能・戻し方 | 公開してよい状態をどう判断するのか | Go / No-Goチェックリスト | 初回有料教材の案内または需要確認 |

## Publication calendar

無料記事は、記事ごとの人間承認後に次の順で公開する。

| Week | Tuesday | Thursday | Friday | Weekend work |
|---|---|---|---|---|
| 1 | #1 | #2 | #3 | 有料教材のサイト仕様・価格調査 |
| 2 | #4 | #5 | — | サンプルサイトの実装 |
| 3 | #6 | #7 | #8 | Mac/Windows再現テスト |
| 4 | #9 | #10 | — | 独立QA、販売条件、公開判断 |

無料10本が揃う前に有料販売を開始しない。週末は有料教材を制作・検証するが、販売はしない。

上表は目標日程である。無料3本の実測工数から残作業を再見積もりし、30日内のNote総時間60時間、通常の週15時間、または当該週の全事業稼働可能時間の半分を超える見込みなら、残りの無料記事または有料教材を翌週以降へ繰り越す。日程のために調査、実機確認、人間承認、品質ゲートを省略しない。

## First paid hands-on

### Working title

**Codexで作る、小さな事業サイト実践ガイド — 静的4ページを設計・検証・公開するまで**

### Reader start state

- 無料記事#1〜#10を読める程度のPC操作ができる。
- 検証済みのMacまたはWindows環境を持つ。
- Codex、Git、GitHub、公開ホストで必要なアカウントを自分で用意できる。
- 自分の事業情報を公開する権限がある。

### Completed artifact

- 最大4ページの静的事業サイト。
  - トップ
  - サービス
  - 会社またはプロフィール
  - プライバシー・運営情報。実際に必要な表示は事業条件ごとに人が確認する。
- GitHubリポジトリ。
- `README`、セットアップ、更新、公開、復旧手順。
- SEO、セキュリティ、アクセシビリティ、性能、プライバシー、リンク、モバイル表示の検査記録。
- 公開前コミットまたはタグと、前バージョンへ戻す手順。

### Initial exclusions

- 認証、ログイン、会員機能
- 決済、予約、契約
- データベース、独自API
- ファイルアップロード
- サイト内問い合わせフォーム
- 顧客・従業員・決済・健康・位置情報等のデータ
- AIチャットボット
- 業界固有の法令適合判断
- SEO順位、集客、売上の保証
- 継続監視、無停止、障害対応、無制限サポート

外部の予約・問い合わせサービスへリンクする場合は、その提供条件、送信先、プライバシー表示を読者本人が確認する。

## Stack selection gate

記事執筆前に一つの実装方式と一つの公開先を固定する。候補を記事内で並列に扱わない。

選定条件:

- Mac/Windowsで同じ成果物を作れる。
- 初学者がクリーン環境から再現できる。
- 静的出力とローカルプレビューが可能。
- 依存関係とライセンスを記録できる。
- HTTPS、プレビュー、独自ドメイン、必要なHTTPヘッダー、ロールバック方法を確認できる。
- 無料枠を使う場合も、上限、商用利用、停止条件、超過時費用を公開前に再確認できる。

初回は、依存関係を最小化した静的HTML/CSS/JavaScript、または一つの静的サイトジェネレーターを比較し、実測した再現性と保守負担で決める。

## Hands-on article structure

1. 完成サイトと対象範囲
2. 必要アカウント、費用、所要時間、対応OS、サポート境界
3. 公開してよい情報・AIへ渡してはいけない情報
4. サイト要件と原稿素材を整理する
5. スターターリポジトリと最初のコミット
6. Codexへ小さく依頼し、差分を確認する
7. 4ページを実装する
8. スマホ表示とアクセシビリティを確認する
9. title、description、見出し、canonical、サイトマップ、robots、OG等を確認する
10. HTTPS、秘密情報、依存関係、外部スクリプト、HTTPヘッダーを確認する
11. ビルド、リンク、404、主要ブラウザ、性能を確認する
12. プレビュー、本番公開、公開URLの再確認
13. 失敗時に前バージョンへ戻す
14. 完成チェックと月次保守

各手順は `目的 → 操作 → 入力例 → 期待結果 → 失敗例 → 修正 → 完了確認` の順で書く。

## Quality gates

| Area | Required evidence |
|---|---|
| Reproducibility | クリーン環境、OS、バージョン、実行日時、全コマンド、実行結果 |
| Code | ビルド成功、依存関係一覧、ライセンス、静的解析または該当チェック、レビュー結果 |
| Security | HTTPS、秘密情報ゼロ、外部スクリプト最小化、依存関係確認、ホスト側ヘッダー、公開リポジトリの全ファイル確認 |
| SEO | ページ別title/description、見出し、canonical、サイトマップ、robots、OG、リンク。順位・インデックスは保証しない |
| Accessibility | 見出し順、代替テキスト、ラベル、キーボード、フォーカス、色、コントラスト、縮小モーション、ズーム |
| Performance | 本番ビルド、画像最適化、不要JavaScript、モバイル計測。固定スコアは保証しない |
| Privacy | 収集情報、外部送信、Cookie、分析、埋め込みの有無。採用時は目的と送信先を表示 |
| Recovery | 公開直前コミット、公開先のロールバック、READMEの復旧手順を実地確認 |
| Editorial | プレースホルダーゼロ、重要主張の一次情報、確認日、権利、価格、非対象、サポート境界 |

「実務で使える」は、この表を通過した静的サイト範囲を意味する。「完全に安全」「プロ品質保証」「SEO対策済みで上位表示」等の表現は禁止する。

### Executable acceptance record

実装方式と公開先を選定した後、上表を具体的な検査表へ展開する。各検査は `check_id / area / criterion / environment / command_or_method / expected_result / actual_result / evidence_path / checked_at / checked_by / result` を持ち、証跡を `company/ventures/note/evidence/note-codex-web-v1/` 配下へ保存する。対象OS、ブラウザ名とバージョン、端末またはviewport、ツールとバージョンも固定する。

一ページ仕様では、少なくとも次を具体値まで決める。

- ビルド、静的解析または代替検査、依存関係確認、リンク・404確認のコマンドと期待終了結果。
- 対象ブラウザ・OS・画面幅、キーボード操作、ズーム、縮小モーション、コントラストの検査方法と合格条件。
- 選定ホストと脅威範囲に応じたHTTPヘッダー名、期待値、確認コマンド、公開URLでの実測結果。
- SEOメタデータ、canonical、サイトマップ、robots、OGの対象ページと確認方法。
- 性能計測のURL、端末条件、ツール、測定日、結果。固定スコアを販売保証にはしない。
- 公開直前の版、ロールバック操作、復旧後URL、復旧確認結果。

検査表、期待値、実測値、証跡のいずれかが欠ける場合、有料公開の品質ゲートは不合格とする。

## Pricing and sale gate

- v1試験価格候補: 980円。
- v1.1候補: 1,480円。両OS検証、スターターコード、更新履歴、共通の失敗対応を追加し、完成確認が得られた後に審査する。
- 購入者は常に最新版を見るため、記事内に `version / updated_at / change_log / tested_environment` を表示する。
- 初回は返金申請を受け付ける設定を推奨するが、設定は人間承認後に行う。
- 無料部分に、完成物、対象、非対象、必要アカウント、別途費用、対応OS、所要時間、目次、サポート範囲を表示する。
- 個別質問への回答期限、デバッグ代行、コードレビュー、導入支援は有料記事に自動付帯しない。

## Cadence gate

### Phase 1

- 4週間で無料10本を目標とする。無料3本後の工数再見積もりで上限超過が見込まれる場合は延長する。
- 土日は初回有料教材の制作、検証、価格調査、QA。
- 有料販売なし。

### Phase 2

- 初回有料記事を一度だけ試験公開。
- 次の有料記事は最低2週間後。
- 質問、返金、修正、完成率、制作時間を確認する。

### Phase 3

隔週2本が重大事故なく完了し、週次時間上限内に収まった場合だけ、毎週末1本を検討する。日付優先で品質ゲートを省略しない。

## Metrics

### Free

- 記事ごとの閲覧・反応・次記事への移動
- 読者のOS、完成した小成果物、停止箇所
- Codex、Git/GitHub、公開、SEO、安全性のどこで質問が集中するか
- 通し手順、テンプレート、トラブル対応への明示的要望

### Paid

- 購入数と純売上。販売予測ではなく実績として記録する。
- 返金申請と理由
- 完成報告と停止工程
- 購入後の質問数、対応時間、教材へ反映した項目
- 重大修正、互換性問題、OS別問題
- v1からv1.1への変更理由

## References

Checked on 2026-08-16:

- OpenAI Docs, Codex CLI: https://learn.chatgpt.com/docs/codex/cli
- OpenAI Docs, ChatGPT desktop app: https://learn.chatgpt.com/docs/app
- OpenAI Docs, Windows app: https://learn.chatgpt.com/docs/windows/windows-app
- OpenAI Docs, WSL: https://learn.chatgpt.com/docs/windows/wsl
- GitHub Docs, About Git: https://docs.github.com/en/get-started/using-git/about-git
- GitHub Docs, What is GitHub?: https://docs.github.com/en/get-started/start-your-journey/what-is-github
- Google Search Essentials: https://developers.google.com/search/docs/essentials
- Google SEO Starter Guide: https://developers.google.com/search/docs/fundamentals/seo-starter-guide
- OWASP HTTP Security Response Headers Cheat Sheet: https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Headers_Cheat_Sheet.html
- OWASP Content Security Policy Cheat Sheet: https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html
- W3C, How to Meet WCAG: https://www.w3.org/WAI/WCAG21/quickref/
