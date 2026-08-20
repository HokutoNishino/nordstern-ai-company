# CEO Decision

Date: 2026-08-17  
Decision ID: NS-2026-009

## Decision

**GO — Nordsternの通常運用を省資源モードへ変更する。**

- 親エージェントは通常 `gpt-5.6-terra` / medium / low verbosityを使う。
- サブエージェントは必要な部門だけを選び、同時実行は原則2部門までとする。
- ルーチン業務はTerraのlow〜mediumを使い、Sol/highは重要リスクのある限定タスクだけにする。
- Fast modeは無効とし、追加クレジット消費を承認した緊急作業だけ例外とする。
- 長期案件はハンドオフを保存し、新しいスレッドへ移して会話履歴の肥大化を抑える。

## Why

プロジェクト設定が個人設定を上書きし、親と3部門をSol相当のモデル/high reasoningで動かしていた。さらに最大5部門を並列実行でき、標準手順も新規案件で全5部門を呼ぶ構造だった。日常的な記事制作や小規模な判断には過剰で、待ち時間と使用量の双方を増やす要因となる。

Fast modeの永続的な選択は確認されなかったため、主因と断定しない。ただし将来の誤操作を防ぐため、プロジェクトでは無効化する。

## Inputs from departments

今回はサブエージェントを起動していない。使用量削減設定のために追加使用量を発生させず、公式仕様とローカル設定の読み取り結果をCEOが直接判断した。

## Assumptions

- 通常の事業整理・記事制作ではTerra/mediumが十分な品質を持つ。
- 現在の長いスレッドを新規スレッドへ切り替えることで、以降に送る文脈量を抑えられる。
- 実際の消費量は契約、タスク、キャッシュ、ツール利用等にも左右されるため、設定だけから削減率は確定できない。

## Rejected alternatives

- Fast modeで速度だけを上げる。対応モデルでは追加クレジットを使うため、今回の二つの目的を同時に満たさない。
- 品質低下の検証なしに、すべてを最小モデル・最低reasoningへ固定する。
- 全5部門の常時並列を維持する。
- 現在の長いスレッドを無期限に継続する。

## Risks

- routine判定を誤り、本来Sol/highが必要な重要案件で分析が浅くなる。
- サブエージェント数を減らすことで、専門的な観点を呼び忘れる。
- 現在のUI上の一時Fast設定など、ファイル外の状態を確認できていない可能性がある。
- 比較対象となるセッション条件が異なると、削減効果を誤評価する。

## KPI / success criteria

次の3つの比較可能なセッションで以下を記録する。

- 開始時と終了時のUI表示上の残使用量。
- 使用したモデル/reasoning、Fast状態、サブエージェント数。
- タスク内容と体感待ち時間。
- 品質上の手戻りの有無。

設定変更前より残使用量の減少が緩やかで、重大な品質手戻りが増えなければ継続する。

## Human approvals required

- 3部門以上を一つの判断で使う場合。
- Fast modeを使う場合。
- 通常運用をSol/highへ戻す場合。

## Next action

新しいスレッドを開いて `続きから` と入力し、Note記事#1の本人確認から再開する。3セッション分の実測後、必要ならTerraのreasoningまたは部門選択ルールを再調整する。

## References

Checked on 2026-08-17:

- OpenAI, Codex speed and Fast mode: https://learn.chatgpt.com/docs/agent-configuration/speed
- OpenAI, Codex configuration basics: https://learn.chatgpt.com/docs/config-file/config-basic
- OpenAI, Codex configuration reference: https://learn.chatgpt.com/docs/config-file/config-reference
- OpenAI, model selection guidance: https://developers.openai.com/api/docs/guides/latest-model
