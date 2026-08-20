# CEO Decision

Date: 2026-08-16
Decision ID: NS-2026-003
Supersedes: NS-2026-002

## Decision

**MODIFY — SES向け事業を停止し、非SES向け受託Web／小規模業務改善を第一事業とする。**

最初の30日間の市場仮説は、小規模不動産事業者とする。入口商品は「問い合わせ対応フロー診断＋固定範囲Web改善」。初期の対象業務は、問い合わせ受信後の対応状況と次アクションの見える化だけに限定する。

自作アプリ／プラットフォームは、受託・ヒアリングを通じて複数社の共通する有料課題が確認できた後の第2段階とする。ECドロップシッピングは、商品カテゴリ、仕入先、粗利、配送、返品、差別化、顧客獲得方法が未定のため、初月は実行しない。

## Why

- SES企業へのサービス提供は勤務先との競業に該当することが判明した。
- 非SES向け受託は、Web制作・Web開発という既存能力を使い、顧客課題を聞いてから小さな固定範囲で提案できる。
- 自作アプリは資産性がある一方、対象利用者、課題、集客経路、支払意思が未検証であり、先行開発のリスクが高い。
- ドロップシッピングは、技術力以外の商品選定、仕入先管理、集客、配送、返品、顧客対応、表示義務の検証が必要で、30日予算3万円では学習が分散する。
- `planner`、`marketer`、`sales`、`developer` の全担当が、第一事業として非SES向け受託を推奨した。
- `qa` は PASS WITH CONDITIONS。競業境界、1業務への限定、架空デモの明示、契約・知財・個人情報の統制を開始条件とした。

## Business model comparison

### 1. Non-SES contract development — selected

- 最初の売上と顧客学習までの距離が比較的短い。
- 顧客課題を確認してから開発範囲を決められる。
- 固定範囲の構築に加え、軽保守・継続改善へ発展できる。
- 主な弱点は、実績不足、要件膨張、人時売上、未払い・検収・保守責任である。

### 2. Own app / platform — second stage

- 成功時には自社資産と継続収益を作れる。
- 現時点では利用者、課題、獲得経路、継続理由、価格が未定。
- プロダクト化の条件は、少なくとも3社で同一の有料課題、近い業務フロー、導入意思、再利用できる実装境界が確認できること。

### 3. EC dropshipping — hold

- 在庫を持たずに始められる可能性はある。
- ただし販売者として、商品説明、広告表示、注文条件、返品、配送、顧客対応、個人情報、仕入先品質を管理する必要がある。
- 商品カテゴリ、信頼できる仕入先、単品粗利、返品・不良率、非価格差別化、獲得チャネルが明確になるまで支出・開店を行わない。

## Target customer hypothesis

- 業種: 小規模不動産仲介・賃貸管理事業者
- 決裁者: 代表、店舗責任者、業務責任者
- 課題仮説: Webフォーム、メール、電話等から来る問い合わせの対応状況と次回行動が分散し、確認・転記・追客に手作業が残る
- 対象外: SES企業、本業の顧客・見込み客・協力会社、本業で知った連絡先や課題を使う相手

不動産であること自体は需要の証拠ではない。独立した経路で決裁者に到達できず、共通課題または支払意思が確認できない場合は対象を再選定する。

## Offer hypothesis

### Step 1: exploratory interview

- 30分程度
- 無償
- 現行フロー、頻度、困りごと、既存ツール、放置コスト、決裁条件を確認
- 顧客データや物件データは受け取らない

### Step 2: workflow improvement mini-design

- 仮説価格: 3万〜5万円
- 成果物: 現行フロー、ボトルネック、改善後フロー、対象範囲、段階導入案
- 実装を発注した場合の充当条件は、見積時に明示する

### Step 3: fixed-scope Web improvement

- 仮説価格: 20万〜50万円
- 対象: 問い合わせの記録、対応状態、担当、次アクションの可視化のうち合意した固定範囲
- 範囲外: 物件DB連携、広告運用、契約判断、決済、LINE・メール自動送信、ネイティブアプリ、無制限修正、24時間保守
- 契約、仕様、着手金、変更管理、検収、知財、秘密保持、個人情報、保守範囲の合意後に着手する

価格は市場相場の主張ではなく、支払意思と採算を検証するための仮説である。

## 30-day priorities

1. 競業境界を、顧客業界、提供内容、営業経路、使用技術・資産の単位で文書化する。
2. 本業由来を排除するため、候補先ごとに連絡先の取得元を記録する台帳を用意する。
3. 不動産の問い合わせ対応について、外部接触前のヒアリング質問票と評価表を作る。
4. 架空データだけを使った1ページのサービス説明とデモ仕様を作る。
5. 外部接触の明示承認後に限り、課題インタビューを実施する。
6. 共通課題が確認された場合だけ、架空データの自主制作デモを1本作る。
7. 有償設計への支払意思が確認できた場合だけ、固定範囲の提案へ進む。

## KPI / success criteria

### Internal preparation gate

- 競業・本業資産の除外ルール: 文書化完了
- 連絡先取得元台帳: 作成完了
- 1業務に限定したサービス定義: 作成完了
- ヒアリング質問票・評価表: 作成完了
- 架空デモ仕様: 作成完了
- 契約・見積・データ取扱いの必須項目: 整理完了

### External validation gate — human approval required

- 適合候補へのヒアリング打診: 10件
- 課題ヒアリング実施: 3件以上
- 同一中核課題の確認: 2件以上
- 架空デモ確認: 2件
- 有償設計への明確な関心または支払意思: 1件以上

30件の適合接触または6週間の検証で支払意思がゼロの場合は、不動産仮説を撤退または再設計する。

## Budget guardrail

30日間の支出上限は合計3万円。外部支出には都度、人間の承認を必要とする。

- ドメイン、メール、最小ホスティング: 1万円以内
- AI・開発支援ツール: 5,000円以内
- 打ち合わせ交通費: 1万円以内
- 予備費: 5,000円以内
- 初月対象外: 広告、外注、EC仕入れ、EC店舗の有料運用、ネイティブアプリ配布費

## Compliance and evidence notes

- 本業の顧客、見込み客、協力会社、情報、コード、テンプレート、営業秘密を使用しない。
- 自主制作物には「自主制作デモ／架空データ」と明記し、顧客実績や改善成果を示唆しない。
- 個人情報を扱う場合は、取得、利用、保存、アクセス、委託、削除、事故対応を定義する。
- 受託成果物の知財帰属は認識だけで決めず、案件ごとに契約へ明記する。
- 不動産取引、物件情報の正確性、契約判断には関与せず、Web・業務フロー支援との責任分界を明示する。

Reference information checked on 2026-08-16:

- Consumer Affairs Agency, Specified Commercial Transactions Act guide for online sales: https://www.no-trouble.caa.go.jp/qa/advertising.html
- Consumer Affairs Agency, advertising guidance including dropshipping: https://www.caa.go.jp/policies/policy/representation/fair_labeling/guideline/assets/representation_cms216_220629_07.pdf
- Personal Information Protection Commission, General Guidelines: https://www.ppc.go.jp/personalinfo/legal/guidelines_tsusoku/
- Apple Developer Program membership details: https://developer.apple.com/jp/programs/whats-included/
- Small and Medium Enterprise Agency, Intellectual Property Transaction Guidelines and contract templates: https://www.chusho.meti.go.jp/keiei/torihiki/chizai_guideline.html
- IPA, Information System Model Transaction and Contract: https://www.ipa.go.jp/digital/model/model20201222.html

## Risks

- 非SES向けWeb改善も、勤務先の実際の事業範囲と重なれば競業になる可能性。
- 独立した新規顧客だけを対象にするため、顧客獲得に時間がかかる。
- 公開実績がなく、有償提案への信頼を得にくい。
- 「小規模事業者のIT担当」という表現が広く、無料相談や要件膨張を招く。
- 個人情報、問い合わせ情報、物件情報の漏えい・誤表示・削除漏れ。
- 低価格の固定契約で修正、サポート、例外対応が増え、採算が崩れる。
- 受託で3社の類似要望が出ただけで、SaaS需要があると誤認する。

## Human approvals required

- 顧客候補への連絡、ヒアリング、価格提示、提案
- サイトまたはデモの公開
- 顧客データまたは匿名化サンプルの受領
- 外部AIサービスへのデータ送信
- ドメイン、サーバー、AI等への支出
- 契約締結、着手金受領、開発着手
- ECの仕入先契約、店舗開設、商品販売、広告出稿

## Next action

外部接触前の内部準備として、「競業・本業資産除外チェックリスト」と「見込み先の取得元台帳」を作成する。その後、不動産向けヒアリング質問票と1ページのサービス定義を作る。
