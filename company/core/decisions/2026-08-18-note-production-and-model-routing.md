# CEO Decision

Date: 2026-08-18  
Decision ID: NS-2026-015

## Decision

**GO — Note制作を5段階の固定工程へ統合し、GPT-5.6のモデルを作業単位で振り分ける。**

- Luna/low: 機械的整理、大量の候補生成、定型更新。
- Terra/low: 軽微な文章判断と短い改稿。
- Terra/medium: 通常の企画、本文、調査統合、実装、QA、CEO判断。
- Sol/high: 重大な安全性・法務・財務・実務品質・設計上の争点だけ。NS-2026-015で単一の限定タスクとして事前承認済みとし、開始前にTerra/mediumでは不足する理由を示して実績を記録する。
- xhighはSol/highで具体的な品質不足が出た場合だけ、maxは創業者の明示承認がある場合だけ。

記事工程は、(1) 企画固定、(2) 候補版制作、(3) 実機・根拠検証、(4) 最終差分レビュー、(5) 人間承認後の公開、に統合する。

## Why

記事#1と#2では、タイトル確定前後の本文・アイキャッチ変更、実機検証後の再修正、複数回のQAとプレビューが手戻りになった。品質ゲート自体は必要だが、未確定の成果物を外部UIへ先に入力したことと、修正を小分けに確認したことが非効率だった。

OpenAI公式はSolを複雑な高品質作業、Terraを知能とコストの均衡、Lunaをコスト重視の大量処理に位置づけ、reasoningはmediumを均衡、lowを低遅延、high/xhighを測定された品質向上がある場合、maxを最難関へ限定している。この区分を会社工程へ適用する。

## Reconciled department advice

- planner: 一つの記事パッケージを唯一の正本にし、未確定制作と再QAを減らす。
- developer: Terra中心を維持し、Lunaは候補生成、Solは重大判断へ限定する。
- CEO: marketerは日本語の読者適合判断を担うためTerra/lowを維持する。salesのみLuna/lowへ変更し、根拠評価が必要なら昇格する。

## Assumptions and unknowns

- API価格の相対差はモデル選定の参考になるが、Codex契約上の残使用量と同一ではない。
- 実際の削減率は未測定。記事#3以降の比較可能な3回で検証する。
- 人間による実機UI確認、権利・個人情報判断、公開承認は自動化しない。

## KPI

各記事で、モデル/effort、サブエージェント数、制作時間、修正バッチ数、QA回数、ブラウザ入力回数、公開後に判明した重大誤り、開始/終了時のUI残使用量を記録する。

合格条件は、重大な品質手戻りを増やさず、原則1回のNote入力、1回の最終QA、1回の公開確認で完了すること。正確な使用量削減率は3件の実測後だけ判断する。

## Human approvals required

- Sol/xhighまたは任意モデル/maxの使用。Sol/highは上記の限定条件内で都度承認不要。
- Fast mode。
- 外部公開、購入、課金、プロフィール変更。

## References

Checked 2026-08-18:

- OpenAI model guidance: https://developers.openai.com/api/docs/guides/latest-model
- OpenAI models: https://developers.openai.com/api/docs/models
