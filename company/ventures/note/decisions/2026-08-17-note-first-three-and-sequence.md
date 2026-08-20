# CEO Decision

Date: 2026-08-17  
Decision ID: NS-2026-008  
Updates: NS-2026-007, NS-2026-006  
Related decisions: NS-2026-004, NS-2026-005

## Decision

**GO — 無料10本の導入順を変更し、#1を自己紹介、#2をChatGPTとCodexの紹介・安全な導入、#3以降を技術記事とする。**

最初の3本は、次の読者状態を順番に作る。

1. #1で、このアカウントの対象、約束、扱わないことを理解し、最初に作りたい成果物を一つ選ぶ。
2. #2で、ChatGPTとCodexの役割を区別し、仕事や顧客情報を含まない練習フォルダで、Codexによる最小のファイル作成を体験する。
3. #3で、Gitを使って変更履歴を残し、確認した未コミット変更を元に戻す。

#2の初心者向け主経路は、ChatGPTデスクトップアプリ内でChatGPTとCodexを使う方法とする。Codex CLI、WSL2、高い権限、追加パッケージ、既存案件での実行は初回導入に含めない。CLIとWSL2は必要性が生じた後の別記事候補とする。

#2と#3は、macOSとWindowsネイティブ環境の両方でクリーンな状態から手順を再現し、画面、所要時間、バージョン、差分、失敗時の復帰方法を記録するまで公開しない。未検証OSを対応対象として表記しない。

## Business objective

- 初心者が「AIを知る」だけで終わらず、HP・LP制作へ進む最初の安全な作業環境を作る。
- 自己紹介を単なる経歴紹介にせず、読者が最初の制作物を選ぶ入口にする。
- AIにコードを変更させる前にGitを学び、以降の記事を変更確認と復旧ができる状態で進める。

## Constraints

- 公開できる顧客実績はない。勤務先、顧客、案件、コード、非公開情報を信用材料に使わない。
- 副業収入、案件獲得、独立、転職、SEO順位、売上を保証しない。
- 初回の技術記事では、認証、決済、データベース、個人情報、顧客情報を扱わない。
- ChatGPT / Codexへ入力または作業対象として渡した内容はサービス上で処理される。Codexによる追加のネットワーク利用を禁止することと、サービスへの入力自体を混同せず、架空の非機密情報だけを使う。
- CodexやChatGPTの利用可否、UI、アカウント条件は変わり得る。公開48時間前に公式情報と実機を再確認する。
- 外部のnoteアカウント、`Note-idea`、公開記事は自動変更しない。本人の明示承認後に手動で反映する。

## Definition of success

- #1を読んだ人が、ポートフォリオ、架空サービスLP、自分の事業・店舗サイトのうち一つを選び、`誰に / 何を伝えるか`を一行ずつ書ける。
- #2を読んだ人が、ChatGPTとCodexの違いを自分の言葉で説明でき、空の練習フォルダ内に意図した`README.md`だけを作れる。
- #3を読んだ人が、親の既存Gitリポジトリ配下でないことを確認したうえで、練習フォルダで`git init`、最初のコミット、`status`と`diff`の確認、意図した未コミット変更の復元を完了できる。
- #2と#3について、macOSとWindowsネイティブの再現記録があり、未確認の画面・コマンド・所要時間が本文に残っていない。
- 各記事が一つの中心課題、一つの小成果物、一つの次行動を持つ。

## Adopted free-series order

| # | Role | Central question | Reader artifact |
|---:|---|---|---|
| 1 | 自己紹介・入口 | このnoteは誰のためで、何を一緒に作るのか | 最初に作りたいものの1分メモ |
| 2 | AI導入 | ChatGPTとCodexは何が違い、どこから安全に始めるのか | 練習フォルダと`README.md`、環境メモ |
| 3 | Git基礎 | AIが変更したものを、どう記録して戻せるようにするのか | ローカルGitリポジトリと最初のコミット |
| 4 | GitHub基礎 | GitとGitHubは何が違い、何を公開してはいけないのか | 公開前チェック付きのリポジトリ計画 |
| 5 | Git/GitHubハンズオン | ローカル履歴を安全にGitHubへ保存するには | 練習リポジトリ、push、復旧確認 |
| 6 | Web通信の基礎 | HTTP/HTTPS、ドメイン、DNS、ホスティングはどうつながるのか | 1ページの公開経路図 |
| 7 | Web三要素 | HTML、CSS、JavaScriptは何を担当するのか | 最小の静的ページ |
| 8 | 制作前設計 | Codexへ頼む前に何を決めればよいのか | 1ページHP・LPの制作ブリーフ |
| 9 | ローカル試作 | 小さく依頼し、差分を見ながら形にするには | ローカルで動く1ページ試作品 |
| 10 | 公開判断 | SEO、安全性、アクセシビリティ、性能、復旧をどう確認するのか | Go / No-Goチェックリスト |

## Inputs from departments

- `planner`は、#1を自己紹介と制作目的の選択、#2を役割理解と最小導入に限定することを推奨した。#2で全機能や全トラブルを扱わず、環境メモを残す案を採用した。
- `marketer`は、#1を読者の制作宣言、#2を最初の安全な成功体験、#3を「AIが触ったものを壊さず育てる」Gitへ接続する導線を推奨した。
- `developer`は、#2を空の練習フォルダと`README.md`一つに限定し、#3をGitHubへ接続しないローカルGit演習にすること、macOSとWindowsネイティブの実機確認を公開条件にすることを推奨した。

## Conflict resolution

`planner`案では#3をHTTP入門とする余地があったが、`marketer`と`developer`はGitを先に置く案を推奨した。CEO判断としてGitを#3に採用する。

理由は、#7以降でHTML等を変更し、#9でCodexに実装を依頼する前に、履歴、差分、復旧という安全装置を読者へ渡す必要があるためである。HTTPは重要だが、コード変更前の安全装置ではないため#6へ移す。

## Assumptions / unknowns

- 初心者はCLIから始めるより、ChatGPTデスクトップアプリでChatGPTとCodexを切り替える方が入口として理解しやすい、という仮説である。完走率の証拠はまだない。
- macOSとWindowsでのクリーン導入、画面文言、実測所要時間は未確認である。
- 読者が最初に選ぶ成果物、利用OS、停止箇所は未確認である。
- 読者反応はNote事業の編集判断に用いるが、不動産・ナイトタイム接客業等の需要証拠には代用しない。

## Rejected alternatives

- #1から用語解説を始め、運営者、読者、到達点を説明しない。
- macOSとWindowsの導入を別記事にして、自己紹介後の技術開始を#4まで遅らせる。
- #2でCLI、WSL2、拡張機能、API、料金比較まで一度に扱う。
- Gitより先にCodexで本格的なHPを作る。
- #3でGitHub公開まで扱い、秘密情報や公開範囲の説明を省略する。
- 未検証のOS手順を「対応済み」として公開する。

## Risks

- #1が運営者中心になり、読者の行動へつながらない。
- #2が製品紹介に偏り、アカウント条件やUI変更で早期に古くなる。
- 初心者が勤務先・顧客フォルダや秘密情報をCodexへ渡す。
- 「追加の外部送信なし」を、ChatGPT / Codexへ入力した内容もサービス上で処理されないという意味に誤解する。
- 練習フォルダを既存Gitリポジトリの中へ作り、親プロジェクトと混同する。
- `git restore`を実案件で使い、未コミット変更を失う。
- WindowsのOneDrive、権限、企業管理端末等の差分を見落とす。
- 3本の制作・検証時間が想定を超え、無料10本の品質を圧迫する。

## Human approvals required

- #1で「現役Webエンジニア」「FDE」「近畿」「バイク」「大阪」を公開すること。
- #1〜#3のタイトル、本文、サムネイル、CTA、公開日。
- #2と#3のmacOS / Windows対応表現と、実機検証結果。
- #2のデータ処理、アカウント設定、組織規程、追加ネットワーク権限の説明。
- アプリ、アカウント、追加課金が必要な場合の支出。記事案に記載されていても自動承認しない。
- Note上の公開、プロフィール変更、読者への返信、`Note-idea`への同期。

## KPI / success criteria

公開後は、いいね数だけで判断せず、次を記事別に記録する。

- 選ばれた最初の成果物と読者目的。任意回答のみ。
- 利用OSと、完了できた小成果物。
- 停止した手順と表示されたエラー。秘密情報は収集しない。
- #1→#2、#2→#3の移動または明示的な次記事要望。
- 制作・検証・修正・問い合わせ対応に使った実時間。

公開後7日指標は、7日経過した記事だけを集計する。30日内に7日経過しない記事は未計測として翌期へ繰り越す。

## Next action

1. #1〜#3のタイトル、目次、本文、サムネイル仕様、出典台帳、公開前レビューを作る。
2. 本人が#1の個人情報と語調を確認する。
3. #2と#3をクリーンなmacOSとWindowsネイティブ環境で通し実行し、未検証箇所を修正する。
4. 独立QAを通し、本人が記事ごとに手動公開を承認する。

## References

Checked on 2026-08-17:

- OpenAI, ChatGPT desktop app: https://learn.chatgpt.com/docs/app
- OpenAI, Codex CLI: https://learn.chatgpt.com/docs/codex/cli
- OpenAI, Windows app: https://learn.chatgpt.com/docs/windows/windows-app
- OpenAI, WSL: https://learn.chatgpt.com/docs/windows/wsl
- OpenAI, Sandboxing: https://learn.chatgpt.com/docs/sandboxing
- OpenAI, Permissions: https://learn.chatgpt.com/docs/permission-modes
- OpenAI, Integrated terminal: https://learn.chatgpt.com/docs/integrated-terminal
- Git, About Version Control: https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control.html
- Git, What is Git?: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
- Git, `git-rev-parse`: https://git-scm.com/docs/git-rev-parse
- GitHub Docs, About Git: https://docs.github.com/en/get-started/using-git/about-git
