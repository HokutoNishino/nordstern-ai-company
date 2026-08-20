# Note Content Automation v0.1

Date: 2026-08-16
Status: Proposed
Decision: NS-2026-005
Integrated reference snapshot: `company/ventures/note/archive/note-idea/`  
Former standalone source retired under NS-2026-012; recoverable at: `/Users/hokuto/.Trash/Note-idea-nordstern-2026-08-17` until Trash is emptied

## Purpose

`Note-idea` にある企画とNote専用Skillsを、NORDSTERNの部門運営へ接続し、記事の企画から公開準備、公開後学習までを再現可能にする。

v0.1の成果は「自動公開」ではない。人間が確認してnoteへ貼り付けられる、根拠・画像・承認記録付きの記事パッケージを安全に作ることである。

## Current assessment

- `Docs/note-idea.md` に、想定読者、提供価値、無料記事、有料ロードマップ、相談・実装への導線がある。
- Note記事用の企画、調査、タイトル、目次、本文、ハンズオン、サムネイル、後書き、レビュー、統合オーケストレーションSkillsがある。
- 第1記事 `001-start-with-work-not-tools` には、ブリーフ、調査、構成、本文、レビュー、サムネイルブリーフが分離されている。
- 第1記事は調査未実施、本文未完成、本人経験未確認、レビュー「要修正」である。
- 旧`Docs/`と`Articles/`は`company/ventures/note/archive/note-idea/`へコピー済み。Note Skillsはグローバル導入版と同一のため重複コピーしていない。検証後、旧単独フォルダはmacOSのゴミ箱へ移動して退役し、書き戻しや双方向同期は行わない。

## Business funnel

```text
無料の実務記事
  → 読者自身の業務棚卸し
  → 無料テンプレート
  → 自力実行向けの有料ロードマップ候補
  → 固定範囲の業務診断候補
  → 合意済み一業務の小規模Web実装候補
  → 必要時のみ運用・改善支援
```

初期3本では、記事から受託へ直接誘導しない。各記事の主CTAは一つの読後行動または次の記事とし、相談導線は対象・提供物・非対象を定義できた後に追加する。

## Department responsibilities

| Department | Responsibility |
|---|---|
| CEO/COO | 事業目的、対象読者、テーマ、優先順位、公開・販売・支出の最終決定 |
| planner | シリーズ目的、記事の役割、無料・有料の価値境界、検証仮説 |
| marketer | 読者課題、ポジショニング、タイトル、記事間導線、CTA、公開計画 |
| sales | 商品梯子、診断への適格条件、誇大な約束の排除、問い合わせ学習 |
| developer | 状態台帳、実行再開、成果物契約、監査ログ、指標取り込み |
| qa | 出典、論理、権利、個人情報、競業、セキュリティ、公開可否の独立判定 |

Note専用Skillsは各成果物の作成を担当し、会社部門は目的・商流・技術・リスクの判断を担当する。

## Workflow and state model

```text
idea_queued
  → brief_ready
  → researching
  → research_ready
  → author_material_required
  → title_outline_ready
  → drafting
  → package_ready
  → qa_review_pending
      ├─ changes_requested
      │    └─ researching | author_material_required | drafting
      └─ human_review_pending
           ├─ changes_requested
           │    └─ researching | author_material_required | drafting
           └─ approved_for_publish
                → copy_package_ready
                    ├─ internal_complete_unpublished
                    └─ [人間が公開]
                         → published_by_human
                         → measuring
                         → closed | update_planned

update_planned
  → researching | author_material_required | drafting
```

`approved_for_publish` は投稿命令ではない。公開承認を得ない記事は `internal_complete_unpublished` をv0.1の合格終端とする。`copy_package_ready → published_by_human` は自動遷移禁止とし、本人がnote URLと公開日時を記録した場合だけ進める。

## Skill sequence

1. `plan-note-series`
2. `research-note-article`
3. `create-note-title`
4. `create-note-toc`
5. `write-note-body` または `write-note-hands-on`
6. `create-note-thumbnail`
7. `write-note-afterword`。必要な場合のみ。
8. `review-note-article`
9. `produce-note-article` が工程と成果物を統合する。

外部情報を扱う記事は、調査Skillを省略できない。各Skillは前工程の成果物を上書きせず、入力版と出力版を記録する。

## Minimum article record

```yaml
id: "001"
slug: "start-with-work-not-tools"
status: human_review_pending
type: explainer
owner: hokuto
audience: "専任IT担当者がいない従業員5〜50名の中小企業経営者"
core_claim: "AI導入はツール選びより業務選定から始める"
reader_action: "繰り返し発生する業務を3つ書き出す"
critical_claims:
  - claim: ""
    source_url: ""
    source_published_at: null
    checked_at: null
    expires_at: null
    primary_source: true
    exception_reason: null
    exception_approved_by: null
quality_gates:
  no_placeholders: false
  sources_current: false
  author_material_verified: false
  rights_checked: false
  competition_checked: false
  reviewer_decision: pending
approval:
  approved_by: null
  approved_at: null
  approved_package_sha256: null
publication:
  note_url: null
  published_at: null
metrics:
  seven_day_recorded_at: null
  twenty_eight_day_recorded_at: null
```

「重要主張」は、誤っていた場合に読者の費用、導入判断、安全、法令・制度対応、製品選択、または記事の中心結論が変わり得る主張とする。料金、製品仕様、制度、統計、セキュリティ情報は公開48時間前に再確認する。それ以外の外部事実も公開審査時に確認日を検査する。一次情報が存在しない、または利用できない場合は、使用した二次情報、一次情報を使えない理由、例外承認者を記録する。

## Required human gates

| Gate | Blocking conditions | Approval record |
|---|---|---|
| Research | 重要主張の裏付け不足、出典と主張の不一致、仕様・料金・制度の確認日なし | 確認者、確認日、出典一覧 |
| Author material | 創作した体験、未確認の実績・費用・時間、顧客・本業情報の混入 | 素材の出所、使用許可、匿名化確認 |
| Editorial | プレースホルダー、過大表現、読者行動不明、無料・有料境界不明 | 対象原稿版、判定、差し戻し理由 |
| Rights and privacy | 第三者文章・画像・商標・肖像・個人情報の確認不足 | 権利確認、出典、使用条件 |
| Publish | 本文・画像・CTA・価格・公開日時の最終確認不足 | 承認者、日時、対象ハッシュ |
| Sale | 提供物、価格、提供時期、問い合わせ、キャンセル等の条件未確認 | 販売条件版、承認者、日時 |

承認後に本文、画像、出典、価格、CTAのいずれかが変わった場合、承認ハッシュを無効とし `human_review_pending` へ戻す。

## 12-article series hypothesis

| # | Type | Theme | Primary reader action |
|---:|---|---|---|
| 1 | 無料・解説 | AI導入はツールでなく業務から始める | 反復業務を3つ書く |
| 2 | 無料・解説 | 最初にAI化しやすい業務5選 | 候補を1つ選ぶ |
| 3 | 無料・ハンズオン | 30分で業務棚卸し表を作る | 棚卸し表を完成する |
| 4 | 無料・解説 | AIで減らしやすい業務・難しい業務の見分け方 | 候補を除外・絞り込む |
| 5 | 無料・解説 | 低コストで始める小さな実証実験 | 試行テーマを決める |
| 6 | 無料・ハンズオン | AI導入の優先順位表を作る | 優先順位表を完成する |
| 7 | 無料・解説 | AI導入前に決める社内ルールの最小セット | ルール草案を作る |
| 8 | 無料・解説 | AIが社内で使われないときに見直すこと | 運用上の障害を一つ選ぶ |
| 9 | 無料・ハンズオン | 30日AI導入計画を作る | 30日計画を完成する |
| 10 | 有料候補 | 生成AI導入ロードマップと実行テンプレート | 自力で計画を実行する |
| 11 | 無料・判断 | 小規模ツール化を検討すべき業務・しない業務 | 仕組み化可否を判断する |
| 12 | 無料・判断 | 既存ツール・外注・自作アプリの選び分け | 必要な支援範囲を定義する |

有料化は公開本数では決めない。#1〜#9で「記入例付きテンプレートと実行順が欲しい」という反応が確認できた場合だけ、#10の無料・有料境界と価格を再審査する。

## First three articles

### #1 AI導入はツールでなく業務から始める

- 目的: ツール比較の前に、反復業務を観察する視点を渡す。
- 不足: 一次情報、本人の検証経験、本文、公開可能判定。
- CTA: 繰り返し発生する業務を3つ書き出す。

### #2 最初にAI化しやすい業務5選

- 目的: AIに任せる候補と、人の判断を残す範囲を具体化する。
- 必須条件: すべての業務で入力、出力、人の確認、失敗時の影響を示す。
- CTA: 自社の候補を1つ選ぶ。

### #3 30分で業務棚卸し表を作る

- 目的: 読者が記事を見ながら一つの成果物を完成できるようにする。
- 成果物: 業務名、頻度、所要時間、入力、出力、判断、機密性、失敗影響、改善候補の表。
- CTA: 棚卸し表を完成し、次の優先順位付けへ進む。

## 30-day MVP

### Days 1–7

- 記事状態台帳、承認記録、品質チェック、貼り付け用パッケージの型を作る。
- 第1記事で使用できる本人経験を収集する。
- 第1記事の一次情報を調査し、重要主張と出典を対応付ける。

### Days 8–14

- 第1記事を完成し、独立レビューと人間承認へ回す。
- 第2記事のブリーフ、調査、構成、本文初稿を作る。

### Days 15–21

- 第2記事を完成する。
- 第3記事と業務棚卸しテンプレートを完成する。

### Days 22–30

- 3記事の制作時間、差し戻し、調査鮮度、AI利用回数を比較する。
- 人間が公開を承認した記事だけ、本人がnote画面へ貼り付けて公開または予約する。
- 公開後7日を経過した記事だけ7日指標を記録する。期間が到来しない記事は未計測として翌期へ繰り越し、MVP失敗とは扱わない。28日指標も期日到来後に記録する。
- 定期Automationを追加するか、手動起動を続けるか判断する。

## Budget control

- 30日間の全事業支出上限は3万円である。
- AI・開発支援ツールの5,000円上限は、3万円に含まれる内枠である。
- 新規課金、note Premium/Pro、画像素材、外部SaaSは、仕様に記載されていても支出承認を意味しない。
- 支出台帳には `date / category_cap / purpose / vendor / planned_amount / approved_by / approved_at / actual_amount` を記録する。
- 承認前の課金と、内枠または総額上限を超える実行を禁止する。

## Acceptance criteria

- 3記事が同じ品質工程を通り、少なくとも `copy_package_ready` または `internal_complete_unpublished` に到達する。
- 人間が公開を承認した記事だけが `published_by_human` へ進み、公開しない記事に公開URL・公開日時を要求しない。
- 各記事に、ブリーフ、調査、構成、本文、画像、レビュー、承認、貼付用成果物がある。
- 公開候補に `[要確認]`、`TODO`、未確認の体験・数値・顧客実績が残らない。
- 重要主張ごとに、出典URL、発行日、確認日、再確認期限がある。一次情報を使えない場合は理由と人間の例外承認がある。
- 第三者素材の権利と個人情報・競業情報の混入を人が確認する。
- 最終承認の対象ハッシュと公開用パッケージが一致する。
- 自動処理はnoteへ投稿、予約、価格変更、SNS投稿、読者返信を行わない。
- 公開しない場合も、公開可能パッケージと内部の制作計測が残る。
- 支出は既存予算枠内で、すべて人間承認を記録する。

## Metrics

### Production

- 工程別の人間作業時間
- AI実行回数と再実行理由
- 差し戻し数と重大度
- 根拠の再確認・差し替え数
- 公開阻害項目の発生数

### Audience, only after publication

- 記事別の閲覧、反応、フォロー
- 主CTAの実行を示す反応
- 具体的な質問と、その読者・課題の適合性
- テンプレート利用意向
- 有料の実行キットまたは限定診断への明示的関心

初期値がないため、数値目標は需要予測として設定しない。最初の3本を比較ベースラインにする。

## Phase 2 automation conditions

3記事後に次を満たした場合だけ、定期実行を追加する。

- 状態遷移と成果物名が安定している。
- 人間レビューの必須指摘が類型化できる。
- 1本当たりの制作費と時間を計測できる。
- 定期実行が主たる顧客発見を圧迫しない。
- ローカルプロジェクトにアクセスできる実行環境を確認できる。

定期実行の候補は、期限到来記事の根拠再確認、レビュー待ち通知、公開後7日・28日の集計、週次レポートである。自動公開、価格変更、外部送信は追加しない。

## Failure and recovery

- 同じ入力版で成功済みの工程は再生成しない。
- 失敗時に直前の有効成果物を保持し、該当工程だけ再開する。
- 取得失敗と、根拠不一致・期限切れを分ける。後者は自動再試行せず調査へ戻す。
- 3回連続で同じ工程が失敗した場合は自動処理を止め、人間へ理由と直前成果物を提示する。
- 秘密情報、顧客情報、認証情報を実行ログへ残さない。

## Explicit exclusions

- noteの非公式API利用
- noteの画面操作による自動投稿・自動予約
- noteアカウント認証情報の保存
- 公開後指標の無許可スクレイピング
- 顧客・本業・前職の非公開情報を使った記事生成
- AIが作った顧客事例、体験談、改善率、推薦コメント
- 無承認の有料化、価格変更、SNS投稿、メール送信、読者返信
- 3本の検証前の独自ダッシュボードと複雑な連携

## References

Checked on 2026-08-16:

- OpenAI, Scheduled tasks: https://learn.chatgpt.com/docs/automations
- OpenAI, Build skills: https://learn.chatgpt.com/docs/build-skills
- note, official API availability: https://www.help-note.com/hc/ja/articles/46643492548121-note%E3%81%8C%E5%85%AC%E5%BC%8F%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%97%E3%81%A6%E3%81%84%E3%82%8BAPI%E3%81%AF%E3%81%82%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B
- note, Premium scheduled posts: https://www.help-note.com/hc/ja/articles/360000279862-note%E3%83%97%E3%83%AC%E3%83%9F%E3%82%A2%E3%83%A0%E4%BC%9A%E5%93%A1%E3%81%A7%E3%81%A7%E3%81%8D%E3%82%8B%E3%81%93%E3%81%A8
- note, creator terms: https://note.com/terms/seller_creators
- note, analytics: https://www.help-note.com/hc/ja/articles/40855099018777-%E3%82%A2%E3%83%8A%E3%83%AA%E3%83%86%E3%82%A3%E3%82%AF%E3%82%B9-%CE%B2-%E8%A8%98%E4%BA%8B%E3%82%92%E5%88%86%E6%9E%90%E3%81%99%E3%82%8B
