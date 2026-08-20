# Note Article Package 002 — ChatGPT and Codex Setup

Article ID: NOTE-FREE-002  
Series: はじめてのAI×WEB  
Decision: NS-2026-008, NS-2026-014  
Package version: 0.6.1  
Prepared: 2026-08-17  
Last revised: 2026-08-19  
Status: `published_manually`  
External publication: Published manually by founder on 2026-08-19 after final edits and preview
Note draft: `https://editor.note.com/notes/n21310a3790ae/edit/`  
Draft save verified: 2026-08-17 (`下書きを保存しました`; persistence rechecked after editor reload)
Publication authorization: The 2026-08-18 authorization applied to v0.5.1 only. Re-publication of v0.6 requires a new explicit founder approval.

## 1. Production brief

### Reader

ChatGPTは聞いたことがあるが、Codexとの違いや、Web制作をどこから安全に始めればよいか分からない初心者。

### Reader start state

- macOSのPCを使える。WindowsとChromeOSは本記事の手順対象外。
- #1の三行メモがある、または練習用の架空テーマを使える。
- ターミナル、Git、プログラミング経験は不要。
- ChatGPT / Codexの利用可否とアカウント条件はまだ確認していない。

### Central issue

ChatGPTとCodexの役割をどう分け、実データを危険にさらさず最初のファイル操作を試すか。

### Reader goal and completed artifact

- Codexへ日本語で依頼し、仕事・顧客・既存制作物から分離した新しい`codex-practice`フォルダを作成してもらう。
- そのフォルダをローカルプロジェクトとして開き、Codexに意図した内容だけを含む`README.md`一つを作成してもらう。
- Codexがチャット内に出した、OS、実施日、フォルダ名、変更ファイル、許可要求の有無を含む結果メモ。ユーザー名を含む完全な保存先は記録しない。
- VS Code内のCodexを開き、`README.md`について「変更しない質問」を一つ実行し、返答とファイル一覧を確認する。

### Not covered

- Codex CLI、WSL2、API、APIキー、API課金
- Windows向けの操作手順、画面説明、動作保証（公式Windowsガイドへの案内だけ掲載）
- Git / GitHub
- 読者自身によるターミナルコマンドの入力、フォルダやファイルの手動作成、コードやMarkdown本文の手入力
- パッケージ追加、Codexによる追加のインターネットアクセス、第三者サービスへの送信、デプロイ
- 管理者権限、フルアクセス、保護解除
- 既存サイト、勤務先・顧客フォルダ、本番コード
- ChatGPTの全機能や他AI製品との比較
- VS Code以外のエディタ

### Target time

未実測。本文では所要時間を断定せず、公開前のmacOS検証結果を基に追記する。

### Success condition

読者が次を確認できる。

- ChatGPTデスクトップアプリ、Codex、VS Code、PCの役割を説明できる。
- ChatGPTは会話による整理、Codexは選択した作業対象のファイル変更、というこの連載での役割分担を説明できる。
- デスクトップアプリを準備し、プロジェクト外の新しいCodexチャットからフォルダ作成を依頼した。
- 保存先と変更予定を読んでから、`codex-practice`一つの作成だけを承認した。
- 作成された`codex-practice`をローカルプロジェクトとして選び、Codexに`README.md`を作成してもらった。
- アプリの変更表示で、選択した`codex-practice`内に、意図した`README.md`以外のファイル変更が表示されていないことを確認した。PC内の他の場所まで確認できたとはみなさない。
- 読者自身はフォルダやファイルを手動作成せず、ターミナルコマンド、コード、Markdown本文を入力していない。
- ChatGPT / Codexへ送る内容がサービス上で処理されることを理解し、架空の非機密情報だけを使った。
- 追加インストール、Codexによる追加のインターネットアクセス、第三者サービスへの送信、管理者権限を許可していない。

## 2. Title

### Recommended

**CodexとVS Code、結局なんやねん？Macで始める安全なAI開発入門**

### Alternatives

1. **Macで始める：ChatGPTとCodexで最初の練習ファイルを作ろう**
2. **Codexは何をしてくれる？初心者がHP制作を始める前の安全な準備**
3. **ChatGPTで考え、Codexで作る。Web制作初心者の最初の30分**

### Selection rationale

本文の中心になったCodexとVS Codeを前半に置き、初心者の率直な疑問をアカウントの語調に合わせた。Mac限定、安全な導入、VS Code内でCodexを使い始める入口という記事の範囲も明示する。

## 3. Table of contents

1. 今日のゴール
2. この記事で使うもの
3. ChatGPTデスクトップアプリとは
4. VS Codeとは
5. VS CodeでCodexを開く
6. 始める前の安全ルール
7. デスクトップアプリを準備する
8. Codexに練習フォルダの作成を相談する
9. 保存先と作成予定を確認する
10. Codexに練習フォルダを作ってもらう
11. 作成されたフォルダをアプリで開く
12. CodexにREADMEを作ってもらう
13. VS CodeでREADMEを確認する
14. 変更内容をアプリで確認する
15. うまくいかないとき
16. 完了チェックと次回予告

## 4. Thumbnail specification

### Selected asset

- File: `assets/002-codex-vscode-setup-thumbnail-v2.png`
- Production record: `assets/002-codex-vscode-setup-thumbnail-v2-record.md`
- Delivered size: 1733 × 908 px（約1.91:1）
- SHA-256: `23aff7a166b00f928112f6c458cbec6ef0cfc1373e12893c274ea0d38cc88dc3`
- v1 remains as historical evidence and is not overwritten.

### Canvas

- Size: 1280 × 670 px
- Background: 淡い生成りまたはごく薄い水色。
- Layout: 左35%に羊の先生、右65%にコピーと簡略図。

### Text

- Main line 1: `CodexとVS Code`
- Main line 2: `結局なんやねん？`
- Sub: `Macで始める安全なAI開発入門`
- Small badge: `初心者向け`

### Visual direction

- 吹き出しアイコンからフォルダアイコンへ矢印を一本つなぎ、`相談・整理 → ファイル作業`を表す。
- OpenAI、ChatGPT、Codexの公式ロゴや製品UIを複製しない。文字名は見出しコピーとしてのみ使用する。
- 画面キャプチャ、コードの細字、複数のOSロゴは使わない。
- #1と同じ羊、濃紺、黄色系アクセントを使い、シリーズの一貫性を保つ。

### Image-generation prompt

> note記事の見出し画像、1280×670。初心者向けの温かいフラットベクター風。左に眼鏡をかけたオリジナルの羊の先生。右に、抽象的な吹き出しアイコンからシンプルなフォルダと一枚の文書アイコンへ向かう一本の矢印。相談してから安全なフォルダ作業へ進む流れを表現。生成り背景、濃紺、落ち着いた黄色、少量の水色。企業ロゴ、製品UI、実在人物、写真、透かしは含めない。画像内文字は指定した三つだけを正確に配置する。

### Rights / privacy checks

- [x] オリジナルキャラクター、生成手段、参照元、図形、利用条件を制作記録へ残した。
- [x] 公式製品ロゴや画面の無断複製を含まない。
- [x] 実機スクリーンショットを使用していない。
- [x] 元画像上で文字と矢印が判別できる。noteの最終プレビューは下書き投入後に確認する。

## 5. Paste-ready article body

以下をnote本文欄へ貼り付ける。記事タイトルは推奨タイトルを別途設定する。`公開前注記`は検証完了後に実測値へ差し替え、本文から削除する。

---

この記事の基本操作は2026年8月17日にmacOSで動作確認済みです。公式情報は2026年8月19日に再確認しています。今回追加したVS Code内のCodex操作も、同じMac環境で確認済みです。図は操作の流れを伝えるためのオリジナルイラストであり、実際の画面ではありません。

前回は、このnoteで最初に作りたいものを三行で決めました。

今回は、Web制作を始めるためのAI環境を準備します。いきなりHPを作るのではありません。仕事のファイルとは完全に分けた練習フォルダで、`README.md`という説明用ファイルを一つだけ作ります。

この記事でCodexへ渡す指示文と確認用メッセージは、コピーしやすいコードブロックにしています。PCでは各ブロックの「コードをコピー」から、その部分だけまとめてコピーできます。端末によってボタンの表記が異なる場合は、ブロック内の文字を選択してコピーしてください。

小さすぎるように見えるかもしれません。でも、AIに何かを作ってもらう前に、次の四つを体験することが大切です。

1. どのフォルダを触らせるか自分で決める
2. 何を変更する予定か先に読む
3. 必要のない権限を許可しない
4. 実際に変わったファイルを自分で確認する

この四つが、これからWeb制作を進めるときの基本姿勢になります。

## 今日のゴール

今日の完成物は、次の三つです。

- Codexが作る空の`codex-practice`フォルダ（途中成果物）
- Codexが作った`README.md`一つ
- 自分の環境を記録した短いメモ

Gitやターミナルは、まだ使いません。今回はVS Codeと公式のCodex拡張機能だけを準備し、AIへ小さく頼んで変更を確認するところまで進めます。

## この記事で使うもの

今回は、次の三つを使います。

- **ChatGPTデスクトップアプリ**：ChatGPTへ相談し、Codexへファイル作業を頼む場所
- **VS Code**：Codexが作ったファイルやコードを見て、変更内容を確認するためのエディタ
- **PC**：アプリと練習ファイルを保存して動かす本体。本記事ではMacを使用

スマートフォンやタブレットだけでは進めません。また、この記事で読者にコードを手入力してもらうこともありません。まずは、それぞれが何をする道具なのかを知っておきましょう。

## ChatGPTデスクトップアプリとは

現在のデスクトップアプリでは、ChatGPTとCodexを選んで作業を始められます。この連載では、二つの役割を次のように分けます。

### ChatGPT：相談して、考えを整理する

たとえば、こんなことを相談します。

- 誰に見せるページにするか
- 一番伝えたいことは何か
- ページに必要な項目は何か
- 初心者向けに用語をかみ砕いてもらう

会話しながら、作る前の曖昧さを減らす役です。

### Codex：選んだ作業場所で、ファイルを扱う

Codexは、選択したフォルダやコードを読み、依頼に応じてファイルを作ったり変更したり、必要な処理を実行したりするためのエージェントです。

便利な反面、作業場所と依頼内容を間違えると、意図しないファイルまで対象にするおそれがあります。せやから最初は、空の練習フォルダと一つのファイルだけに絞ります。

ChatGPTが「一緒に考える机」、Codexが「指定した作業台で手を動かす相手」と考えると、最初は分かりやすいでしょう。

公式のデスクトップアプリ案内では、アプリをインストールしてサインインし、作業場所を選び、ChatGPTまたはCodexを選んで始める流れが示されています。この記事では、そのデスクトップアプリを初心者向けの主経路にします。詳しい手順は[ChatGPT desktop appの公式ガイド](https://developers.openai.com/codex/app)で確認できます。

## VS Codeとは

VS Codeは、Microsoftが提供するコードエディタです。コードエディタとは、Webサイトやアプリを構成するファイルを開き、内容や変更箇所を見やすく確認するためのアプリです。

この連載では、読者に長いコードを書き写してもらう使い方はしません。基本はCodexへ日本語で依頼し、VS Codeでは「どのファイルがあるか」「どこが変わったか」「表示された内容が依頼どおりか」を確認します。いわば、AIが行った作業を見るための作業机です。

VS Codeは個人利用でも商用利用でも無料です。CodexをVS Code内で使うには、公式の**拡張機能**を追加します。開いているファイルや選択した部分を文脈として渡し、質問、変更の依頼、変更内容の確認を同じ画面で行えるようになります。

### 今回のVS Codeの準備

この記事は、筆者が使っている**MacBookでのmacOS操作**を基準に進めます。Windowsでは画面と権限の流れが異なるため、この記事の手順は案内しません。

まだ入っていない方は、[VS Code公式サイト](https://code.visualstudio.com/)からmacOS版をダウンロードしてインストールし、一度起動できるところまで確認します。検索広告や非公式の配布サイトからは入れないでください。

会社管理のMacでは、自分でインストールせず、会社の規程と管理者の指示を優先します。

- [VS Code公式FAQ](https://code.visualstudio.com/docs/supporting/faq)
- [OpenAI公式：Codex IDE extension](https://learn.chatgpt.com/docs/codex/ide)

## VS CodeでCodexを開く

VS Codeの左側にある拡張機能アイコンを開き、検索欄へ`Codex`と入力します。検索結果から直接入れるのではなく、上の[OpenAI公式ガイド](https://learn.chatgpt.com/docs/codex/ide)にあるインストールリンクを開いて、公式の拡張機能であることを確認してから追加してください。

![操作イメージ1：VS Codeで拡張機能を追加する入口。実際の画面とは異なります。](assets/002-vscode-extension-entry-illustration-v1.png)

*操作イメージ1（実際の画面とは異なります）*

公式性は図では判断せず、公式ガイドのインストールリンク、提供元が`OpenAI`であること、拡張機能IDが`openai.chatgpt`であることの3点で確認します。

追加後は、左側の**Codexアイコン**を選びます。見当たらない場合は、`⌘`+`Shift`+`P`でコマンドパレットを開き、`Codex: Open Codex Sidebar`を実行してください。はじめて使う場合は、画面の案内に従って自分のChatGPTアカウントでサインインします。

![操作イメージ2：VS Codeの横でCodexとの会話欄を開く流れ。実際の画面とは異なります。](assets/002-vscode-codex-sidebar-illustration-v1.png)

*操作イメージ2（実際の画面とは異なります）*

拡張機能は、VS Code本体と同じ範囲のファイルへアクセスできます。だから、ここで仕事用フォルダや既存サイトを開かないことが大切です。この記事では、後で作る`codex-practice`だけを開きます。

## 始める前の安全ルール

次のルールを守ってください。

- 勤務先、顧客、実案件、既存サイトのフォルダを選ばない
- パスワード、APIキー、秘密鍵、顧客情報、個人情報を入力しない
- ChatGPTやCodexへ入力した文章と、作業対象として渡す内容はサービス上で処理される前提で、架空の非機密情報だけを使う
- 自分のアカウントのデータ設定、利用条件、組織のAI利用規程を確認する
- 管理者権限やフルアクセスを有効にしない
- 内容が分からない許可要求は、いったん拒否する
- Codexによる追加のインターネットアクセスや、第三者サービスへの送信を許可しない
- 会社管理のPCでは、会社の規程と管理者の指示を優先する

ここでいう「追加のインターネットアクセスや第三者サービスへの送信を許可しない」は、ChatGPT / Codexへ何も送信されない、という意味ではありません。プロンプトを送って回答を得たり、選んだファイルを作業対象にしたりする以上、その内容は利用中のサービスで処理されます。だからこそ、この記事では公開してよい架空情報だけを使います。

Codexには、ローカル操作の範囲を制限し、インターネット利用や作業範囲外の操作について確認を求める権限モードがあります。今回は`Ask for approval`を選び、人が追加操作を確認できる状態にします。`Full access`は使いません。ただし、許可画面が出たこと自体は安全の証明ではありません。何を、なぜ許可するのか分からなければ、止まって大丈夫です。仕組みの概要は[Permissionsの公式ガイド](https://developers.openai.com/codex/permission-modes)と[Sandboxingの公式ガイド](https://developers.openai.com/codex/sandboxing)で確認できます。

## デスクトップアプリを準備する

インストールは、検索広告や非公式の配布サイトではなく、[OpenAI公式のデスクトップアプリ案内](https://developers.openai.com/codex/app)から進めます。公式案内には複数OS向けの入口がありますが、この記事で操作を案内するのはmacOSだけです。

### macOSで準備する

公式ページからmacOS向けの案内を選び、インストール後にアプリを開いて、自分のChatGPTアカウントでサインインします。

表示される機能や利用条件は、アカウントや管理設定、時期によって異なる場合があります。Codexが表示されない場合、非公式ツールを入れたり、この記事だけを理由に新しい課金を始めたりせず、現在のアカウントと公式案内を確認してください。

サインインできたら、次の三つを確認します。

1. 作業相手として`Codex`を選ぶ
2. 権限モードを`Ask for approval`にする
3. 既存プロジェクトを開かず、プロジェクト外の新しいチャットを始める

画面の文言はアプリの版によって少し変わる場合があります。`New chat`や「新しいチャット」に近い表示を探してください。この時点では、仕事用、顧客用、既存サイトのフォルダを開きません。`Full access`も選びません。

## Codexに練習フォルダの作成を相談する

ここから先も、読者がフォルダを手作業で作ったり、コードを書いたりする必要はありません。Codexへ日本語で指示を出し、作業前の説明を読んでから許可します。

作成場所には「現在のユーザーのホームフォルダ直下」を指定します。ホームフォルダとは、そのPCを使っている自分専用の基本フォルダです。

完全な保存先にはユーザー名が含まれる場合があるため、チャットには表示させません。この記事では`~/codex-practice`という、ユーザー名を隠したmacOSの省略表記で確認します。許可画面に完全な保存先が表示されても、画面の写真や文字列をSNSやコメント欄へ載せないでください。

プロジェクト外のCodexチャットへ、次の指示文をそのままコピーして送ります。

```text
私はPC操作とプログラミングの初心者です。
練習専用の新しいフォルダを1つ作りたいです。

フォルダ名: codex-practice
作成場所: 現在のユーザーのホームフォルダ直下

まだ何も作成しないでください。
既存のファイルやフォルダは、開く・読む・変更・削除しないでください。
ホームフォルダの中身を一覧表示しないでください。
同じ名前のフォルダがすでにある場合は、内容を開かず、
何も変更せずに止めてください。

まず次の3点だけを日本語で説明してください。
1. 作成場所の省略表記
   ~/codex-practice と表示し、
   ユーザー名を含む完全な保存先はチャットに表示しないでください。
2. 作成するもの
3. 必要になる許可

私が「この場所に作成して」と返すまで、何も変更しないでください。
Full access、管理者権限、追加のインターネットアクセス、
第三者サービスへの送信は使わないでください。
```

最初の返答では、説明だけが表示されれば正解です。まだフォルダが作られていなくても、失敗ではありません。先に作業予定を確認するため、わざと止めています。

## 保存先と作成予定を確認する

Codexの返答を、次の順番で確認します。

- 作成場所が`~/codex-practice`と省略表示されている
- 新しく作るものは、空のフォルダ一つだけ
- 既存のファイルやフォルダを開いたり、一覧表示したりしない
- この段階では、フォルダ内にファイルを作らない
- `Full access`、管理者権限、追加のインターネットアクセスを求めていない

ユーザー名を含む完全な保存先がチャット本文に表示された場合も、作成を許可せずに止めます。許可画面に表示された場合は自分の画面で対象だけを確認し、コメント欄やSNSには貼り付けません。

一つでも違っていたら、作成を許可しません。チャットへ「何も変更せずに止めてください」と送り、そこで終了します。

## Codexに練習フォルダを作ってもらう

保存先と作成内容がすべて合っていたら、次の文をコピーして送ります。

```text
説明した場所と内容で問題ありません。
codex-practice フォルダ1つだけを作成してください。
完了後は、作成場所をユーザー名のない省略表記で報告してください。
ユーザー名を含む完全な保存先はチャットに表示しないでください。
```

許可画面が出たら、表示された操作が`codex-practice`フォルダ一つの作成だけか確認します。ホームフォルダ全体の読み取り、`Full access`、管理者権限など、範囲の広い許可を求められた場合は拒否してください。

この手順でCodexがフォルダを作れない環境も考えられます。その場合、権限を広げて無理に続けません。「うまくいかないとき」まで進んでください。

## 作成されたフォルダをアプリで開く

Codexから作成完了の報告が出たら、デスクトップアプリの`Open folder`や「フォルダを開く」に近い項目を選びます。先ほど作成された`codex-practice`だけを選び、ローカルプロジェクトとして開きます。

ここだけは、作業対象をアプリへ教えるための選択操作です。読者がフォルダを新規作成したり、中へファイルを追加したりする操作ではありません。

開いた後、アプリに表示される作業場所の名前が`codex-practice`であることを確認します。その一つ上のホームフォルダや、デスクトップ、書類フォルダ全体を選んではいけません。名前が違う場合は、メッセージを送らずに閉じます。

ローカルプロジェクトは、選んだフォルダをチャットの作業対象として使うためのものです。プロジェクト外のチャットとローカルプロジェクトの違いは、[Projects and chatsの公式ガイド](https://learn.chatgpt.com/docs/projects)でも確認できます。

## CodexにREADMEを作ってもらう

`codex-practice`を開いた状態で、新しいCodexチャットを始めます。次の指示文をコピーして送ってください。記号や文章を自分でファイルへ書く必要はありません。

```text
現在の作業場所が codex-practice フォルダであることを確認してください。
違う場合は何も変更せずに止めてください。
ユーザー名を含む完全な保存先は表示せず、
~/codex-practice と省略して表示してください。

README.md だけを新規作成し、次の内容を書いてください。

# Codex 練習
- 作りたいもの: 1ページWebサイト
- 見てほしい人: 初心者の制作物を見る人
- 伝えたいこと: 学んだ内容と自分で作ったもの

まだファイルを作成しないでください。
まず変更予定と、作成するファイル名だけを示してください。
私が「実行して」と返すまで何も変更しないでください。

追加インストール、追加のインターネットアクセス、
第三者サービスへの送信、
他のファイルやフォルダの作成・変更・削除は行わないでください。
```

Codexが示した予定を読みます。合格条件は、次のとおりです。

- 新しく作るのは`README.md`だけ
- 書く内容は、依頼した見出しと三つの箇条書きだけ
- インストール、追加のインターネットアクセス、第三者サービスへの送信をしない
- 他のフォルダやファイルに触れない

予定が違っていたら、実行しません。「何も変更せずに止めてください」と返します。

予定どおりなら、次の文をコピーして送ります。

```text
作業場所と変更予定は正しいです。
今後、ユーザー名を含む完全な保存先は表示せず、
~/codex-practice と省略して表示してください。

予定どおり、README.md 1つだけを作成してください。
他のファイルやフォルダは変更しないでください。
実行して。
```

追加の許可を求められたら、内容と理由を読みます。今回の仕事に不要な権限なら拒否します。

## VS CodeでREADMEを確認する

`codex-practice`をVS Codeで開き、左側のCodexアイコンを選びます。最初に行うのは、ファイルを変えない質問です。`README.md`を開いてから、次の文をコピーして送ります。

```text
開いている README.md の3行目に書かれている「見てほしい人」を、そのまま教えてください。
ファイルの作成・変更・削除はしないでください。
インストール、追加のインターネットアクセス、第三者サービスへの送信はしないでください。
```

返答を読んだら、VS Codeのエクスプローラーでファイルが`README.md`一つだけであることを確認します。この時点では、Codexへ変更を頼みません。まず「開いているファイルの内容を読める」ことと、「依頼していない変更をしない」ことを確かめるためです。

![操作イメージ3：READMEを開き、変更しない質問をして内容を確かめる流れ。実際の画面とは異なります。](assets/002-vscode-readme-check-illustration-v1.png)

*操作イメージ3（実際の画面とは異なります）*

## 変更内容をアプリで確認する

作業が終わったら、Codexの報告だけで完了にしません。デスクトップアプリの変更表示を開き、次を確認します。ファイル管理アプリで探したり、`README.md`を自分で編集したりする必要はありません。

- 新しく増えたファイルは`README.md`だけか
- `README.md`に、依頼した見出しと三つの箇条書きがあるか
- 既存ファイルの変更や削除が表示されていないか
- 内容に個人情報や秘密情報が入っていないか

一つでも違っていたら、そこで止めます。追加の作業を頼まず、何が変わったかを記録してください。

最後の記録もCodexに作ってもらいます。ただし、PC内へ新しいファイルは増やさず、チャットに結果を表示するだけです。次の指示文をコピーして送ります。

```text
これ以上ファイルを変更せず、今回の結果を確認してください。
ユーザー名を含む完全な保存先は表示せず、
作成場所は ~/codex-practice と省略してください。
次の形式でチャットに報告してください。

OS:
実施日:
作業フォルダ名:
作業場所: ~/codex-practice
新規作成したファイル:
変更・削除した既存ファイル:
追加の許可要求:
完了条件を満たした: はい / いいえ

最後に README.md の現在の内容をそのまま表示してください。
```

表示された結果を読んで、先ほど自分が確認した変更表示と一致するか確かめます。`作業フォルダ名`は`codex-practice`、`作業場所`は`~/codex-practice`になっていれば正解です。完全な保存先やユーザー名は、公開場所へコピーしないでください。

ここで確認できるのは、アプリが`codex-practice`内の変更として表示した範囲です。この画面だけで、PC内の他の場所に一切影響がなかったと証明できるわけではありません。だからこそ、作業前に対象を一つへ絞り、範囲の広い許可を拒否することが大切です。

これが、今後の手順で問題が起きたときに環境差を切り分ける最初の記録になります。

## うまくいかないとき

### Codexが表示されない

利用できる機能や条件が現在のアカウントと一致しているか、公式案内を確認します。会社や学校の管理アカウントでは、管理者の設定が優先される場合があります。制限を回避しようとせず、個人で利用してよい環境かを確認してください。

### プロジェクト外のチャットからフォルダを作れない

環境やアプリの版によって、プロジェクト外のチャットで利用できるファイル操作が異なる可能性があります。`Full access`へ切り替えたり、ホームフォルダ全体を作業対象にしたりせず、何も変更せずに終了してください。

これは読者の操作ミスとは限りません。この記事の手順と現在のアプリが合わない可能性があるため、止まった見出しとOSだけを記録します。手作業でフォルダを作る代替手順は、この記事では案内しません。

### 同じ名前のフォルダがすでにある

上書き、削除、中身の確認はしません。既存の`codex-practice`には触れずに終了してください。別名でやり直す場合は、指示文にある名前をすべて`codex-practice-01`へ変更し、最初の相談からやり直します。

### フォルダを選ぶのがこわい

それで正常です。Codexが作成した`codex-practice`だけを選びます。一つ上のホームフォルダ、デスクトップ、書類フォルダ全体は選びません。場所が分からない、仕事用かもしれない——どちらかに当てはまるなら、何も選ばずに閉じます。

### 予定外のインストールや権限を求められた

VS Code本体とOpenAI公式のCodex拡張機能以外は、今回は不要です。承認せずに止めます。この記事の完成物は、`README.md`一つと、変更しない質問への返答です。

### 「外部送信しない」なら、入力内容はPCの外へ出ない？

いいえ。ChatGPT / Codexへ送ったプロンプトや、作業対象として渡した内容は、利用中のサービスで処理されます。この記事で禁止しているのは、Codexが今回の作業に不要な追加のインターネットアクセスを行うことや、第三者サービスへ送信することです。入力前に、自分のアカウントのデータ設定、利用条件、組織の規程を確認し、架空の非機密情報だけを使ってください。

### `README.md`以外も変わった

それ以上の依頼は出しません。アプリの変更表示に出たファイル名を控え、練習フォルダ外への影響が疑われる場合はCodexを停止します。原因が分からないまま作業を続けないでください。

## 完了チェック

- [ ] 公式案内からアプリを準備した
- [ ] VS Codeを公式サイトから準備し、起動できることを確認した
- [ ] OpenAI公式ガイドからCodex拡張機能を追加した
- [ ] VS CodeでCodexサイドバーを開き、`README.md`への変更しない質問を送った
- [ ] VS Codeのエクスプローラーで、意図しないファイルが増えていないことを確認した
- [ ] 権限モードを`Ask for approval`にし、`Full access`は使わなかった
- [ ] プロジェクト外のCodexチャットで、作成前の説明を読んだ
- [ ] Codexに`codex-practice`フォルダ一つだけを作ってもらった
- [ ] 読者自身はフォルダやファイルを手動作成せず、コードやMarkdownを書いていない
- [ ] アプリで、作成された`codex-practice`だけを選んだ
- [ ] Codexの変更予定を読んでから`README.md`の作成を許可した
- [ ] アプリの変更表示で、作られたのは意図した`README.md`だけだと確認した
- [ ] 変更表示の確認範囲は、選択した`codex-practice`内に限られると理解した
- [ ] 入力・選択した内容がサービス上で処理されることを理解し、架空の非機密情報だけを使った
- [ ] アカウントのデータ設定、利用条件、組織のAI利用規程を確認した
- [ ] 追加インストール、追加のインターネットアクセス、第三者サービスへの送信、不要な権限を許可していない
- [ ] Codexがチャットに出した結果メモと、アプリの変更表示が一致した

全部確認できたら、ChatGPTとCodexの最初の使い分けは完了です。

ただし、今のフォルダには、まだ変更履歴がありません。次回はGitを使い、AIが作ったファイルを「いつ、どんな状態で保存したか」分かるようにします。そのときも、読者がコマンドやコードを手入力するのではなく、Codexへ小さく依頼し、実行予定と変更内容を自分で確認する流れで進めます。

---

## 6. CTA

Primary CTA embedded in body: have Codex create the isolated practice folder and one-file artifact, inspect both approval scope and app change view, and complete the chat-only environment memo without manual file creation or code entry.

Optional feedback prompt, subject to human approval:

> どのmacOSバージョンで試しましたか？ 止まった見出しとあわせて教えてください。画面の個人情報、完全なファイルパス、会社名、エラー内の秘密情報は投稿しないでください。

## 7. Important-claim and source ledger

| ID | Important claim | Primary source | Published / updated | Checked | Recheck rule | Status |
|---|---|---|---|---|---|---|
| C1 | ChatGPT desktop appの公式クイックスタートは複数OS向けの入口を持ち、ChatGPTまたはCodexを選んで始める流れを示す。本記事の操作対象はmacOSだけ | https://developers.openai.com/codex/app | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication; verify the macOS UI | Source supports the general entry route; macOS practical validation remains required |
| C2 | Codexは選択した作業場所のファイルを読み、編集し、依頼に必要な処理を実行できる | https://developers.openai.com/codex/app | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication | Source supports capability and desktop workflow |
| C3 | Codexのsandboxとapprovalは別の制御で、sandboxは到達範囲を制限し、approvalは追加操作について確認する | https://developers.openai.com/codex/sandboxing | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication | Source supports claim |
| C4 | WindowsにはmacOSとは別の公式ガイドがあり、本記事ではWindows向け操作を扱わず、そのガイドへの案内だけを掲載する | https://learn.chatgpt.com/docs/windows/windows-app | Page date not displayed | 2026-08-17 | Recheck link within 48 hours before publication | Source supports the scope disclaimer; no Windows compatibility or procedural claim is made |
| C5 | 利用できる機能・条件は現在のアカウントや管理設定で確認が必要 | Official app/account UI; no plan-specific assertion made | Not applicable | 2026-08-17 | Human verifies actual account and current official account documentation before publication | Deliberately non-specific; validation required |
| C6 | デスクトップアプリの権限モードはローカルファイル編集、コマンド、インターネット利用等の追加操作を制御し、`Ask for approval`は作業範囲外やインターネット利用前に人へ確認する | https://developers.openai.com/codex/permission-modes | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication; validate the selected mode on macOS | Source supports claim; macOS UI validation remains required |
| C7 | `Full access`は作業フォルダ外の操作も許し、データ損失・漏えい・予期しない動作の危険を大きくする | https://developers.openai.com/codex/permission-modes | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication | Source supports warning; article instructs readers not to use it |
| C8 | プロジェクト外のチャットを開始でき、ローカルフォルダを作業対象にする場合はローカルプロジェクトとして開く | https://learn.chatgpt.com/docs/projects | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication; verify current labels on macOS | Source supports projectless chat and local-project distinction; it does not promise arbitrary folder creation from a projectless chat |
| C9 | 現行Macアプリにはプロジェクト外チャットとローカルフォルダ追加の別導線があり、対象限定の承認で`~/codex-practice`を作成できた | Installed `/Applications/ChatGPT.app` v26.810.52044 static UI resources and founder-operated runtime | App inspected and runtime-tested 2026-08-17 | 2026-08-18 | Recheck current labels before publication | Core route and final no-change check passed on the documented Mac |
| C10 | VS Codeは個人・商用とも無料で利用できる | https://code.visualstudio.com/docs/supporting/faq | Updated 2026-02-04 | 2026-08-18 | Recheck within 48 hours before publication | Official FAQ explicitly supports the claim |
| C11 | VS Codeは何百万人もの開発者に使われ、公式サイトから8万件を超える拡張機能を参照できる | https://code.visualstudio.com/ | Page date not displayed | 2026-08-18 | Recheck within 48 hours before publication | Current official homepage supports both statements; counts can change |
| C12 | CodexにはVS Code向け公式拡張機能があり、Codexアイコンまたはコマンドパレットからサイドバーを開き、開いているファイルや選択範囲を文脈に質問・変更・レビューできる | https://learn.chatgpt.com/docs/codex/ide | Page date not displayed | 2026-08-19 | Recheck within 48 hours before publication; validate the clean macOS flow and screenshots | Official OpenAI IDE-extension guide supports the procedure; clean-workspace runtime validation remains required |
| C13 | VS Code拡張機能はVS Code本体と同じ権限で動作するため、公式ガイドから提供元を確認して追加する | https://code.visualstudio.com/docs/configure/extensions/extension-marketplace | Updated 2026-02-04 | 2026-08-19 | Recheck within 48 hours before publication | Official extension-security guidance supports the warning |

No price, plan entitlement, performance, completion-rate, or security-guarantee claim is made. If the final draft names a plan or price, add a separate claim row and recheck it within 48 hours of publication.

## 8. Practical validation record

### Evidence currently available

- 2026-08-17 read-only local check: macOS 26.6.1（Build 25G76）、Apple Silicon（arm64）。
- `/Applications/ChatGPT.app`を確認。bundle IDは`com.openai.codex`、short versionは`26.810.52044`、buildは`6662`、minimum macOSは`13.0`。
- 同梱UI文字列に、プロジェクト外で始める`New standalone chat`と、ローカルプロジェクトを追加する`Open folder`の別導線があることを確認した。
- 分離した一時フォルダで、空の状態から`README.md`一つだけを作る成果物を再現した。SHA-256は`8b502426c98acafb48a941b4eb2c4780ad18812de888233115dc1f6f3f510d84`。
- 人が操作する実機確認で、プロジェクト外チャットから対象限定の許可を経て`~/codex-practice`だけを作成できた。`Full access`、管理者権限、追加のインターネットアクセスは使用していない。
- 作成したフォルダをローカルプロジェクトとして開き、実行前の変更予定を確認した後、`README.md`一つだけを作成できた。アプリの変更表示は`+4 / -0`で、作成内容とSHA-256が分離環境での期待値に一致した。
- README作成前の確認返答でユーザー名を含む完全な保存先が表示されたため、公開用プロンプトには`~/codex-practice`で省略表示する指示を追加した。最終結果メモと、その依頼による追加変更なしの確認は未完了。
- 現時点の証拠はほぼ完了しているが、クリーンインストール、所要時間、すべての初心者環境での再現性までは検証していない。
- 2026-08-19 read-only check: macOS版VS Code 1.133.0で、OpenAI提供の`openai.chatgpt`拡張機能と`Open Codex Sidebar`の入口を確認した。既存作業領域には個人情報・会話履歴があり、公開用スクリーンショットの取得や記事手順の実行には使用していない。
- 2026-08-19 practical check: 新しいVS Codeウインドウで`~/codex-practice`だけを開き、CodexサイドバーからREADMEを読む質問を実行した。`README.md`以外のファイルは表示されず、作成・変更・削除・追加インターネットアクセス・第三者サービス送信の許可要求も出なかった。最初の「初心者向けに3行で説明」質問は意図が広く、応答が一意にならなかったため、公開原稿の確認質問をREADMEの特定行を読む形式へ修正した。
- v0.6.1では実機スクリーンショットを使わず、操作の概念を示すオリジナルイラスト3点を追加した。イラストは実際のUI・製品ロゴ・画面文言を再現せず、公式拡張機能の確認根拠には用いない。
- 2026-08-17の創業者判断NS-2026-014により、記事#2の操作・検証・公開範囲をmacOSだけに限定した。Windowsについては公式ガイドへの案内以外の動作主張をせず、Windows環境の検証を公開条件にしない。
- The current automation environment cannot operate the ChatGPT desktop app UI without bypassing its safety restriction. macOS runtime validation requires a human-operated app run; this is an evidence limitation, not a product failure.

### Required macOS run

- [ ] Clean or documented fresh-user environment.
- [ ] OS version and hardware recorded without publishing personal identifiers.
- [ ] Official download path and final URL recorded.
- [ ] App version/build and account type/management status recorded.
- [x] `Ask for approval` selected and `Full access` disabled.
- [x] Exact visible route to Codex, projectless new chat, and local-folder selection recorded.
- [x] Planning prompt caused no change before explicit approval.
- [x] Projectless chat created only the exact home-folder `codex-practice` path; folder-creation chat used `~/codex-practice` rather than a username-bearing full path.
- [x] No home-folder listing, unrelated read, or broad permission request occurred.
- [x] Created `codex-practice` alone was opened as the local project, not its parent directory.
- [x] README planning prompt caused no change before execution approval. The original prompt allowed a username-bearing full path in the planning response; the public prompt is corrected.
- [x] Only `README.md` changed; before/after evidence saved.
- [x] Chat-only result memo caused no further file change and matched the README/change evidence. Its original `作成したフォルダ名` field was ambiguous across two chats, so the public schema was corrected to `作業フォルダ名` and `作業場所`.
- [ ] Review evidence is described as limited to changes displayed within the selected local project; no whole-device assurance is inferred.
- [ ] All permission prompts and decisions recorded.
- [ ] Time measured from official-page opening to completion.
- [ ] Common failures and recovery verified.

### Windows scope decision

- Article #2のWindows向け操作、画面説明、再現性評価はNS-2026-014により対象外。
- 本文にはOpenAI公式のWindows appガイドへの案内だけを掲載する。
- Windowsで同じ操作ができるという互換性・動作保証・サポートの主張はしない。
- このmacOS限定記事の公開条件としてWindows実機検証を要求しない。

上の未チェック項目は、初回の実機検証で未測定だった補足証跡であり、v0.6.1の公開条件ではない。v0.6.1の公開条件は「Human approval checklist」に集約する。そこで必須としたmacOSのVS Code手順の実機確認が未実施または失敗なら、公開せずに手順を見直す。

## 9. Afterword decision

**Omit.** The completion checklist and Git bridge already provide a clean close. A personal reflection would lengthen a first-install article without helping the reader verify success.

## 10. Pre-publication review

### Editorial result

**PASS WITH REQUIRED VALIDATION — v0.6.1の構成・安全境界は整合している。VS Code拡張機能のクリーンな実機確認と独立QAは完了。操作イラストを入れたnote最終プレビューと再公開承認が未完了。**

**v0.6.1 self-review — 2026-08-19:** VS Code内でCodexを開く導線と、`README.md`へ変更しない質問をする導線を追加した。不要な「プラグイン」表現とPCスペック／Chromebookの説明を外し、MacBook基準の記事であることだけを残した。読者にコードの手入力は求めない。実機画面の代わりに、実画面ではないことを明記したオリジナル操作イラストを3点追加し、公式性の確認は公式ガイド・提供元・拡張機能IDで行うよう本文に分離した。

**v0.6.1 independent QA — 2026-08-19: PASS WITH CONDITIONS.** 図が実画面に見えないこと、公式性の確認根拠の分離、実機確認記録、公開ゲートを確認した。条件だった本文中の可視キャプションと、旧実機メモの公開条件からの分離は反映済み。note最終プレビューと再公開承認は残る。

**v0.5.1 release review — 2026-08-18: PASS.** The final memo and read-only artifact check closed the runtime gate. The ambiguous cross-chat `作成したフォルダ名` field was corrected to `作業フォルダ名` / `作業場所`; no unverified success claim or username-bearing path remains in the public body.

### Release result

**NOT READY FOR FINAL HUMAN APPROVAL — v0.6.1の操作イラストを入れたNote最終プレビューと再公開の個別承認が未完了。**

### Independent draft-entry QA

**PASS — 2026-08-17, confidence high, for v0.4 scope consistency.** Independent QA found no implied Windows support, no active Windows release gate, and no stale cross-platform prompt outside the clearly retired worksheet. This result does not cover the v0.5 VS Code / PC additions or corrected privacy prompts; release review must be repeated after validation closes.

### Review notes

- Accuracy: All current product claims are tied to official OpenAI sources. No plan or pricing claim is made.
- Reader fit: No terminal or Git prerequisite; the reader copies instructions, reviews plans, approves exact operations, and selects only the created folder. Folder/file creation and Markdown entry are delegated to Codex.
- Logic: Explain roles → establish rules → prepare app → ask Codex to plan the isolated folder → approve exact creation → open that folder → plan and create one file → inspect.
- Reproducibility: The core folder and README creation route and the final no-change check have been reproduced on the documented Mac. Full setup time remains unmeasured, so the public body makes no duration promise.
- Security/privacy: Strong exclusion of work/client data, secrets, unnecessary additional internet access and privileges. The draft explicitly distinguishes service processing of submitted context from agent-initiated additional network access and does not imply that sandboxing guarantees safety.
- Evidence boundary: The draft now avoids sending a username-bearing full path in chat and states that the app change view covers the selected local project, not the whole PC.
- Scope: macOS is the only procedural target. Windows receives a respectful scope notice and an official-guide link, with no compatibility claim. CLI, APIs, package install, GitHub, and production work are correctly deferred.
- CTA: Completion can be verified without posting a screenshot or personal information.

### Validation resolutions

1. The stop notice was replaced with the tested macOS date and the official-information recheck date.
2. The measured core run was approximately 14 minutes; full setup was not measured, so the public body makes no duration promise.
3. Current labels are described with tolerant wording where app versions may differ.
4. v0.6.1では、実機スクリーンショットではなくオリジナル操作イラスト3点を追加した。本文と代替テキストで実画面ではないことを明示している。
5. Observed privacy and cross-chat memo issues were corrected in the public prompts/schema.
6. v0.5.1の公式情報は2026-08-18に確認済み。v0.6は公開直前に全リンクを再確認する。
7. Narrow approval succeeded; `Full access` and the home folder as a broad project were not used.
8. The privacy-safe `~/codex-practice` target passed the folder-creation route. The README prompt now repeats the same display restriction.

## 11. Human approval checklist

- [ ] 推奨タイトルを承認した。
- [ ] ChatGPT / Codexの役割説明が現在の公式仕様と一致する。
- [x] macOSの実機検証証跡を確認した。
- [x] Windows向け操作は対象外とし、公式ガイドへの案内だけにする方針を承認した（NS-2026-014）。
- [x] macOS限定であること、所要時間、アカウント条件の表現を承認した。
- [ ] 課金や新規アカウントが必要な場合、別途支出を承認した。記事案は支出承認ではない。
- [x] ChatGPT / Codexへ入力・選択した内容がサービス上で処理される説明を承認した。
- [x] アカウントのデータ設定、利用条件、組織のAI利用規程を確認した。
- [x] フォルダ作成プロンプトが`codex-practice`一つだけを要求し、既存内容の一覧・読取・変更を禁止している。
- [x] ファイル作成プロンプトが`README.md`一つ以外を要求していない。
- [x] プロジェクト外チャットからのフォルダ作成が、`Full access`やホームフォルダ全体の選択なしで再現できた。
- [x] チャットにユーザー名を含む完全な保存先を表示せず、省略表記で対象を確認できた。
- [x] アプリの変更表示が証明する範囲を、選択したローカルプロジェクト内に限定して承認した。
- [x] `~/codex-practice`だけを開いたVS Codeで、Codex拡張機能の追加・サイドバー表示・変更しない質問を実機確認した。
- [x] 操作イラスト3点が実UI・製品ロゴ・画面文言を複製せず、実画面ではない旨を本文と代替テキストに明記した。
- [x] v0.6.1の公開48時間以内に、公式情報とリンクを再確認した（2026-08-19）。
- [x] v0.6.1の独立QAが、操作イラスト・実機確認・プレビュー条件を確認し、条件付きで通過と判断した。条件のうち原稿修正分は反映済み。
- [ ] v0.6.1のnote最終プレビューを本人が確認し、再公開を個別に承認した。

## 12. Note private-draft record

### Publication record — 2026-08-19

- Founder manually completed final edits, preview, and publication of Article #2.
- The canonical local package documents the reviewed v0.6.1 draft. Any final manual adjustments made directly in Note must be re-read from Note before a future update so that the public article remains the source of truth for the next revision.

- Draft ID: `n21310a3790ae`
- Editor URL: `https://editor.note.com/notes/n21310a3790ae/edit/`
- Saved title: `CodexとVS Code、結局なんやねん？Macで始める安全なAI開発入門`
- Note editor count: 9,790 characters
- Structure verified after save and editor reload: H2 × 15, H3 × 12, code blocks × 5, links × 11
- Copyability: folder planning prompt, exact folder-creation approval, README planning prompt, `実行して`, and the chat-only environment memo are separate native Note code blocks; current public desktop rendering was checked to expose `コードをコピー` for native code blocks.
- Workflow revision: after app preparation, Codex plans and creates the isolated folder; the reader only copies instructions, reviews/approves the exact target, selects the created folder in the app, and reviews the resulting project-local change display. No manual folder/file creation or code/Markdown entry is required.
- Privacy/evidence limits: username-bearing full paths are excluded from chat in favor of the `~/` form; the draft states that the app change view does not prove absence of changes elsewhere on the Mac.
- Copy guidance, the revised workflow, and the macOS-only scope notice were saved to the private draft on 2026-08-17. The ChatGPT desktop app / VS Code / Mac environment explanations and privacy-corrected prompts were saved on 2026-08-18.
- v0.6 revision status: the Note article was returned to draft on 2026-08-19. The local canonical copy has been revised for the VS Code extension flow, image plan, Mac-only environment note, and removal of the unnecessary「プラグイン」wording; this v0.6 body has not yet been entered or saved in Note.
- Eyecatch v2: `assets/002-codex-vscode-setup-thumbnail-v2.png`; generated, uploaded, cropped, saved, and verified in Note's actual desktop preview on 2026-08-18.
- Save evidence: note displayed `下書きを保存しました`; the editor was reloaded and the 9,790-character v0.5.1 revision, 15 H2 headings, 12 H3 headings, five code blocks, 11 links, title, and eyecatch persisted.
- Publication action: **performed with explicit founder approval** at 2026-08-18 14:23 JST. Public URL: `https://note.com/witty_ram1894/n/n21310a3790ae`.
- Scope revision: NS-2026-014 limits Article #2 to macOS. The Windows worksheet is retired from this article's release gate; the article keeps only a respectful official-guide pointer.
- v0.5 revision: added beginner explanations for the ChatGPT desktop app, VS Code, and the Mac used in the series. v0.6 subsequently simplified this to a MacBook-based explanation and removed the PC-specification and Chromebook discussion.
- Runtime result after v0.5.1 correction: **PASS for the documented Mac**. The core folder and README creation route passed, the final memo caused no additional file change, and the artifact remained 4 lines / 181 bytes with SHA-256 `8b502426c98acafb48a941b4eb2c4780ad18812de888233115dc1f6f3f510d84`.
- Actual Note desktop preview: PASS on 2026-08-18. Title, creator name, validated opening, 15 H2 headings, 12 H3 headings, five code blocks, links, and eyecatch rendered; the 1492px viewport had no page-level horizontal overflow and all code blocks fit their containers.
- New-title/eyecatch desktop preview: PASS on 2026-08-18. The sheep teacher, all four exact text strings, editor/folder motif, title, and article structure rendered without clipping or page-level horizontal overflow.
- Public-page verification: PASS on 2026-08-18. Title, creator name/profile, opening, eyecatch, H2 × 15, H3 × 12, five native code blocks with copy controls, and tags `#ChatGPT`, `#プログラミング初心者`, `#web制作`, `#Codex`, `#VScode` were present. No preview banner appeared.
- Publication settings: free; creator-page display ON; automatic translation OFF; AI compensation program OFF; comments ON; no magazine, coupon, scheduled publication, or social share.
