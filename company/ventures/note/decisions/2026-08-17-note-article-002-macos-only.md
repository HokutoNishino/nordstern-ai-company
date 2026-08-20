# Article #2 macOS-only release scope

Date: 2026-08-17  
Decision ID: NS-2026-014  
Updates: NS-2026-008  
Status: Adopted

## Decision

Article #2の操作手順、実機検証、再現性評価、公開条件をmacOSだけに限定する。

Windows利用者には、記事がmacOS向けであり画面・保存先表記・権限画面が異なることを伝え、OpenAI公式のWindows appガイドを案内する。Windowsで同じ操作ができるという互換性、動作保証、個別サポートは主張しない。

Windows実機検証はArticle #2の公開条件から外す。既存のWindows検証シートは削除せず、`out_of_scope_by_founder_decision`として履歴を保つ。

## Why

- 創業者が2026-08-17にWindows対応を行わない方針を明示した。
- 初心者向け記事では、未検証のWindows手順をmacOSと同じものとして案内しない方が誠実である。
- 現在の公開候補手順をmacOSで深く検証することに、制作・検証時間を集中できる。

## Assumptions and limits

- この判断はArticle #2だけを更新する。Article #3以降の対応OSは、各記事の内容と検証環境に基づき別途決める。
- Windowsの公式ガイドへのリンク掲載は、Windows手順の検証済み表示やサポート提供を意味しない。
- macOSの中心手順は未検証であり、この方針変更だけでは公開可能にならない。

## Release gate

公開前に次を完了する。

1. macOSで、`Ask for approval`を維持したプロジェクト外チャットから`~/codex-practice`だけを作成できるか実機検証する。
2. `Full access`、ホームフォルダ全体の選択、無関係ファイルの読取を使わない。
3. 公開48時間以内に公式情報とリンクを再確認する。
4. 独立QAとnote最終プレビューを通す。
5. 既に得た公開許可は、上記条件を満たした後の公開操作にだけ使用する。

## Next executable task

創業者がmacOS版ChatGPTデスクトップアプリで、記事パッケージの`Required macOS run`を実行し、匿名化した結果を検証シートへ記録する。
