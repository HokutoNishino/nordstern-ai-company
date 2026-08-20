# Note Article Package 003 — Git Basics

Article ID: NOTE-FREE-003  
Series: はじめてのAI×WEB  
Decision: NS-2026-008  
Package version: 0.1  
Prepared: 2026-08-17  
Status: `validation_required`  
External publication: Blocked until clean macOS and native Windows validation, independent QA, and human approval

## 1. Production brief

### Reader

#2でCodexに一つの練習ファイルを作らせたが、変更履歴、差分、戻し方を知らないWeb制作初心者。

### Reader start state

- ChatGPTデスクトップアプリで、練習専用の`codex-practice`フォルダを選べる。
- そのフォルダには、公開してよい架空内容の`README.md`だけがある。
- そのフォルダは、既存サイト、既存制作物、勤務先・顧客フォルダの中に作っていない。
- GitHubアカウントは不要。
- 既存案件、勤務先、顧客、公開中サイトは使わない。

### Central issue

AIが変更したファイルを、ローカルのGitでどう記録し、差分を確認し、意図した未コミット変更だけを戻すか。

### Reader goal and completed artifact

- `codex-practice`をローカルGitリポジトリにする。
- `README.md`と練習用`index.html`を明示的に追加し、最初のコミットを作る。
- 一つの使い捨て変更を`status`と`diff`で確認する。
- データ消失の警告を理解したうえで、その未コミット変更だけを`git restore`で元へ戻す。
- OS、Gitバージョン、コミットID、最終状態をメモする。

### Not covered

- GitHubへの接続、公開・非公開設定、push
- ブランチ、merge、rebase、チーム開発
- `git reset --hard`、force push、履歴改変
- `git add .`による一括追加
- 既存リポジトリや実務データ

### Target time

30〜45分の編集仮説。**未実測であり、本文の所要時間表記は公開前のmacOS / Windows検証結果に置き換える。**

### Success condition

- 最初のコミットを`git log --oneline -1`で確認できる。
- `git init`の前に親リポジトリの有無を確認し、既存リポジトリ内なら中止している。
- 戻す前に、対象ファイルと差分を自分で確認している。
- `git restore -- index.html`の後、`git status`がクリーンな状態を示す。
- `README.md`、コミット、他のファイルを意図せず失っていない。

## 2. Title

### Recommended

**Gitって何？AIで作ったHPを壊さず育てるための最初の一歩**

### Alternatives

1. **Git入門：Codexが変えたファイルを記録して、確認して、戻してみよう**
2. **GitとGitHubは別物です。まずはPCの中で変更履歴を作ろう**
3. **AIにコードを任せる前に覚えたい、Gitの保存と復元の基本**

### Selection rationale

抽象的な「バージョン管理」より、AI利用時の初心者不安である「壊したらどうする」を入口にした。ただし本文では、Gitが事故を自動防止するわけではないこと、未記録の変更は失い得ることを明示する。

## 3. Table of contents

1. 今日のゴールと大事な注意
2. Gitは「変更の節目を残す道具」
3. GitとGitHubは別物
4. 練習フォルダとGitの場所を確認する
5. Gitを使い始める
6. 練習用のHTMLを一つ作る
7. 最初のコミットを作る
8. 変更を確認してから元に戻す
9. よくあるつまずき
10. 完了チェックと次回予告

## 4. Thumbnail specification

### Canvas

- Size: 1280 × 670 px
- Background: 生成り。
- Layout: 左に羊の先生と一枚のWebページ、右に大きなコピー。

### Text

- Main: `Gitって何？`
- Sub: `AIで作ったHPを壊さない`
- Small label: `変更を記録して戻す`

### Visual direction

- Webページのカードを三枚、少しずつずらして重ね、時系列のスナップショットを表す。
- 一番新しいカードから一つ前へ戻る短い矢印を置く。
- GitやGitHubの公式ロゴ、ターミナル画面の細かな文字、赤い警告だらけの表現は使わない。
- 危険操作を扱うため、`戻せる＝絶対安全`に見える盾や保証マークは使わない。

### Image-generation prompt, if later approved

> note記事の見出し画像、1280×670。初心者向けのシンプルなフラットベクター。左に眼鏡をかけたオリジナルの羊の先生、その横に少しずつずれた三枚のブラウザー風カード。新しいカードから一つ前のカードへ戻る短い矢印で、変更履歴と復元を抽象的に示す。生成り背景、濃紺、落ち着いた黄色、少量の緑。企業ロゴ、Gitロゴ、GitHubロゴ、製品UI、実在人物、写真、透かし、画像内文字は含めず、右側に大きな日本語タイトルを後入れできる余白を残す。

### Rights / privacy checks

- [ ] キャラクター、フォント、図形の権利と利用条件を記録した。
- [ ] Git / GitHubの公式ロゴを無断使用していない。
- [ ] 実機画面を使う場合、ユーザー名、パス、メール、組織、リポジトリ名、通知、秘密情報を除いた。
- [ ] 「完全に安全」「必ず戻る」と誤認させるコピーや図形がない。

## 5. Paste-ready article body

以下をnote本文欄へ貼り付ける。記事タイトルは推奨タイトルを別途設定する。`公開前注記`は検証完了後に実測情報へ差し替え、本文から削除する。

---

> **公開前注記：** この記事は現在、macOSとWindowsネイティブ環境での最終検証前です。全コマンド、表示、失敗時の復帰、所要時間を両OSで確認するまで公開しません。

前回は、空の`codex-practice`フォルダで、Codexに`README.md`を一つだけ作ってもらいました。

ここからHTMLやCSSを作り始める前に、変更の節目を残せるようにします。使うのはGitです。

「Git、黒い画面、英語。急にエンジニアっぽさが三段跳びしてきたな」と感じるかもしれません。今回はGitHubへ公開しません。練習フォルダの中だけで、次の四つを試します。

1. Gitを使い始める
2. 最初の状態を記録する
3. 変更箇所を見る
4. 確認済みの練習変更を一つだけ元に戻す

## 今日のゴールと大事な注意

完成したとき、練習フォルダには最初のコミットが一つ残ります。

その後、`index.html`へ使い捨ての一文を追加し、差分を見てから元に戻します。

> **重要：** `git restore`は、コミットしていない変更を破棄することがあります。今回は、練習専用の`index.html`へ自分で追加した一文だけを、`git status`と`git diff`で確認してから戻します。既存案件、仕事、顧客、本番サイトでは実行しないでください。

また、Codexへ送るプロンプトや、作業対象として渡す内容は利用中のサービスで処理されます。前回と同じく、公開してよい架空の非機密情報だけを使います。「追加のインターネットアクセスを許可しない」は、サービスへ何も送られないという意味ではありません。

途中で表示が記事と違う、対象フォルダに自信がない、残したい変更が混ざっている——どれかに当てはまる場合は、コマンドを止めます。

## Gitは「変更の節目を残す道具」

Gitは、ファイルの変更を時間の流れに沿って記録し、過去の状態を確認できるバージョン管理システムです。

この連載では、写真にたとえて考えます。

- ファイルを変更する：撮影前に机の上を動かしている状態
- `git add`：次の写真に写すものを選ぶ
- `git commit`：選んだ状態を、説明付きの節目として記録する

Gitは、作業中のすべてを勝手に守ってくれる道具ではありません。コミットしていない変更は、操作によって失うことがあります。だからこそ、`status`で対象を確認し、節目ごとにコミットします。

Gitの公式解説では、変更を`modified`、`staged`、`committed`という状態で扱います。今は「変更した」「次の記録に選んだ」「記録した」の三段階として覚えれば十分です。

## GitとGitHubは別物

名前が似ていますが、GitとGitHubは同じものではありません。

- **Git**：PCの中で変更履歴を管理する仕組み
- **GitHub**：Gitのリポジトリをネット上で保存・共有・レビューできるサービス

今回はGitだけを使います。ネットへ公開せず、練習フォルダの中で履歴を作ります。

GitHubは次回、公開範囲と秘密情報の確認から始めます。「Gitを使った＝GitHubに公開された」ではありません。

## 練習フォルダとGitの場所を確認する

ChatGPTデスクトップアプリで、前回の`codex-practice`フォルダを現在の作業対象として開きます。

アプリ内のターミナルを開きます。公式ガイドでは、各チャットの統合ターミナルは現在のプロジェクトまたはworktreeを作業範囲とし、Git操作にも使えると説明されています。詳しくは[Integrated terminalの公式ガイド](https://learn.chatgpt.com/docs/integrated-terminal)を確認してください。

最初に、現在地を確認します。

### macOS

```bash
pwd
ls
```

### Windows PowerShell

```powershell
Get-Location
Get-ChildItem
```

確認するのは二点です。

- 現在地の最後が`codex-practice`になっている
- 一覧に、前回作った`README.md`がある

勤務先、顧客、別の制作物の名前が見えたら、そこで止めます。正しい練習フォルダを選び直し、もう一度現在地を確認します。

フォルダ名が正しくても、既存のGitリポジトリの中へ`codex-practice`を作っている可能性は残ります。たとえば、既存サイトのフォルダ内に練習フォルダを作ると、親のGit管理と混ざるおそれがあります。名前だけでは安全確認になりません。

## Gitを使い始める

Gitが使えるか確認します。macOSとWindowsのどちらも、同じコマンドです。

```bash
git --version
```

`git version`に続いて番号が表示されたら、次へ進みます。その番号は、あとで環境メモに残します。

コマンドが見つからない場合は、非公式の配布サイトや見覚えのないインストーラーを使いません。[Git公式のインストール案内](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)から、自分のOS向け手順を確認します。インストール後はアプリを開き直し、現在地を再確認してから`git --version`をもう一度実行します。

### 既存の親リポジトリではないことを確認する

`git init`を実行する前に、現在のフォルダまたは親フォルダが、すでにGitで管理されていないか確認します。macOSとWindowsのどちらも同じコマンドです。

```bash
git rev-parse --show-toplevel
```

新しい練習フォルダなら、`not a git repository`を含むエラーが表示されます。この手順では、それが期待する結果です。まだGitリポジトリではなく、親の既存リポジトリにも入っていないことを示します。

反対に、フォルダのパスが表示された場合は、`git init`を実行しません。現在地または親フォルダが、すでにGitリポジトリです。

その場合は次のようにします。

1. 表示されたパスをメモし、それ以上コマンドを実行しない
2. その既存リポジトリの外に、新しい空の`codex-practice-safe`フォルダを作る
3. #2の手順に戻り、架空内容の`README.md`一つだけを新しいフォルダへ作る
4. 新しいフォルダを作業対象として開き、現在地と`git rev-parse --show-toplevel`をもう一度確認する

既存リポジトリを削除、移動、初期化して解決しようとしないでください。この記事は、完全に分離した練習フォルダだけを対象にします。

次に、このフォルダでGitを使い始めます。

```bash
git init
```

`git init`は、このフォルダへGitの管理情報を用意します。GitHubへの送信や公開は行いません。

環境によっては、最初のブランチ名に関する`hint`と、`git config --global`を含む例が表示されます。これは失敗ではありません。この記事ではPC全体の設定を変えないため、その例は実行せず、そのまま次の`git status`へ進みます。

状態を確認します。

```bash
git status
```

最初は`README.md`がまだ記録対象に選ばれていない、つまり未追跡のファイルとして表示されるはずです。表示が違う場合は、そのまま次へ進まず、現在地とフォルダの中身を確認します。

## 練習用のHTMLを一つ作る

Codexへ、次の依頼を送ります。

```text
このフォルダは練習専用です。

index.html だけを新規作成し、内容を次のとおりにしてください。

<!doctype html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Git練習</title>
</head>
<body>
  <h1>Git練習</h1>
  <p>最初の状態を記録します。</p>
</body>
</html>

まず変更予定だけを示し、私が「実行して」と返すまで
ファイルを変更しないでください。
追加インストール、追加のインターネットアクセス、
第三者サービスへの送信、
他のファイルの作成・変更、Git操作は行わないでください。
```

予定が`index.html`一つの新規作成だけなら、`実行して`と返します。

作業後、状態を確認します。

```bash
git status
```

`README.md`と`index.html`が未追跡ファイルとして表示されることを確認します。見覚えのないファイルがあれば、追加しません。

## 最初のコミットを作る

次のコミットへ入れるファイルを、名前で明示して選びます。

```bash
git add README.md index.html
```

この練習では`git add .`を使いません。フォルダ内のすべてを一括で選ぶと、意図しないファイルや秘密情報を含めるおそれがあるためです。

選んだ状態を確認します。

```bash
git status
```

`README.md`と`index.html`が、次のコミットに入る新しいファイルとして表示されていることを確認します。

最初のコミットを作ります。

```bash
git commit -m "Create practice page"
```

### 名前とメールのエラーが出た場合

Gitは、コミットへ記録する名前とメールアドレスを求めます。今回の練習フォルダだけに、練習用の値を設定します。

```bash
git config user.name "Practice User"
git config user.email "practice@example.invalid"
```

`--global`を付けていないため、設定対象はこの練習リポジトリだけです。この練習用メールは、後でGitHubアカウントへ結び付けるための値ではありません。GitHubへ進むときは、公開範囲とメールの扱いを別途確認します。

設定後、もう一度コミットします。

```bash
git commit -m "Create practice page"
```

記録できたか確認します。

```bash
git log --oneline -1
git status
```

短い英数字と`Create practice page`が表示され、`git status`が変更なしを示せば、最初の節目を記録できています。

## 変更を確認してから元に戻す

ここからは、戻す練習です。Codexへ次の依頼を送ります。

```text
練習用の index.html だけを変更してください。

既存の段落の後に、次の段落を1つ追加してください。
<p>この一文は、差分を確認してから元に戻します。</p>

他のファイル、Gitの履歴、設定は変更しないでください。
追加インストール、追加のインターネットアクセス、
第三者サービスへの送信は行わないでください。
```

変更後、まず状態を確認します。

```bash
git status
```

変更されたファイルが`index.html`だけであることを確認します。

次に、実際の差分を見ます。

```bash
git diff -- index.html
```

追加した一文だけが差分に含まれることを確認します。

> **ここでもう一度確認：** 次の`git restore`を実行すると、`index.html`の未コミット変更を破棄します。残したい変更が一つでもある場合は実行しません。今回は、今追加した使い捨ての一文だけであることを確認済みのときだけ進みます。

確認できたら、`index.html`を最後にコミットした状態へ戻します。

```bash
git restore -- index.html
```

最後に確認します。

```bash
git status
git diff -- index.html
```

`git status`が変更なしを示し、`git diff`に何も表示されなければ、練習変更だけを元に戻せました。

ブラウザーで`index.html`を開き、次を確認します。

- `Git練習`という見出しがある
- `最初の状態を記録します。`という文章がある
- 戻す練習で追加した一文は消えている

## よくあるつまずき

### `not a git repository`と表示された

`git init`前の親リポジトリ確認で表示された場合は、期待する結果です。その後に`git init`を実行していれば、別の場所にいる可能性があります。新しいコマンドを試す前に、macOSは`pwd`、Windowsは`Get-Location`で現在地を確認します。

### `git rev-parse --show-toplevel`でパスが表示された

現在地または親フォルダが、すでにGitリポジトリです。`git init`を実行せず、本文の「既存の親リポジトリではないことを確認する」へ戻って、表示されたリポジトリの外に新しい練習フォルダを作ります。

### `git`が見つからない

Gitのインストールが完了していないか、インストール前から開いていたアプリが古い環境を見ている可能性があります。公式案内を使い、インストール後にアプリを開き直して確認します。

### 名前とメールを求められた

本文の「名前とメールのエラーが出た場合」へ戻り、この練習リポジトリだけに設定します。いきなり全リポジトリ共通の設定にしません。

### `README.md`や`index.html`以外も表示された

追加しません。`git add .`も実行しません。現在地とファイル一覧を確認し、練習フォルダに意図しないものが混ざった原因を先に調べます。

### `git restore`する前に不安になった

止まるのが正解です。`git status`と`git diff -- index.html`を見直します。残したい変更か判断できなければ、実行しません。

## 完了チェック

- [ ] 現在地が`codex-practice`で、実案件ではないと確認した
- [ ] Codexへ渡す内容がサービス上で処理されることを理解し、架空の非機密情報だけを使った
- [ ] `git --version`の結果を記録した
- [ ] `git rev-parse --show-toplevel`が、初期化前に`not a git repository`を示した
- [ ] `git init`の後に`git status`を確認した
- [ ] `README.md`と`index.html`だけを名前で指定して追加した
- [ ] 最初のコミットを作り、`git log --oneline -1`で確認した
- [ ] 戻す前に、対象が`index.html`だけと確認した
- [ ] `git diff -- index.html`で使い捨ての一文だけを確認した
- [ ] 警告を理解してから`git restore -- index.html`を実行した
- [ ] 最後の`git status`が変更なしを示した

最後に、次の環境メモを残します。公開時は完全なファイルパスや個人情報を載せません。

```text
OS:
実施日:
Gitバージョン:
最初のコミットID（短い英数字）:
最後のgit status: 変更なし / 要確認
つまずいた手順:
```

これで、AIが変更する前後に節目を作り、差分を見て、確認済みの未コミット変更を戻す最初の練習ができました。

次回はGitHubを扱います。Gitとの違い、公開リポジトリと非公開リポジトリ、パスワードやAPIキーを載せないための確認から始めます。まだネットへ送らなくて大丈夫です。

---

## 6. CTA

Primary CTA embedded in body: complete the local repository exercise and environment memo.

Optional feedback prompt, subject to human approval:

> macOS / Windowsのどちらで試し、どの見出しで止まりましたか？ 完全なパス、メールアドレス、会社名、顧客名、ファイル内容、秘密情報は投稿せず、OSと見出し名だけでも大丈夫です。

## 7. Important-claim and source ledger

| ID | Important claim | Primary source | Published / updated | Checked | Recheck rule | Status |
|---|---|---|---|---|---|---|
| C1 | バージョン管理はファイルの変更を時間とともに記録し、後で特定の版を呼び戻せる | https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control.html | Page version/date not displayed | 2026-08-17 | Recheck before publication | Source supports claim |
| C2 | Gitはファイルをスナップショットとして扱い、modified / staged / committedの状態を持つ | https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F | Page version/date not displayed | 2026-08-17 | Recheck before publication | Source supports claim |
| C3 | `git init`は既存ディレクトリをGitリポジトリとして初期化できる | https://git-scm.com/docs/git-init | Manual page date not displayed | 2026-08-17 | Recheck commands on both OS before publication | Source supports claim; practical validation missing |
| C4 | `git status`はworking treeの状態を表示する | https://git-scm.com/docs/git-status | Manual page date not displayed | 2026-08-17 | Recheck commands on both OS before publication | Source supports claim; practical validation missing |
| C5 | `git restore`はworking treeのファイルを復元し、未コミット変更を失わせ得る | https://git-scm.com/docs/git-restore | Manual page date not displayed | 2026-08-17 | Recheck command and warning on both OS immediately before publication | Source supports claim; destructive-step validation missing |
| C6 | ChatGPTデスクトップアプリの統合ターミナルは現在のproject/worktreeに紐付き、Git操作に使える | https://learn.chatgpt.com/docs/integrated-terminal | Page date not displayed | 2026-08-17 | Recheck within 48 hours before publication and validate current UI | Source supports claim; practical validation missing |
| C7 | GitとGitHubは別で、GitHubはGitリポジトリをホストし共同作業等に使えるサービス | https://docs.github.com/en/get-started/using-git/about-git | Page date not displayed | 2026-08-17 | Recheck before #4 publication | Source supports claim |
| C8 | `git rev-parse --show-toplevel`は作業ツリーの最上位ディレクトリを表示でき、初期化前の親リポジトリ検出に使える | https://git-scm.com/docs/git-rev-parse | Manual page date not displayed | 2026-08-17 | Recheck behavior on both OSes before publication | Source supports claim; practical validation completed only on current Mac temp directory |

The draft makes no guarantee that Git prevents loss, that all changes are recoverable, or that a repository is safe to publish.

## 8. Command inventory and risk classification

| Command | Purpose | Writes state | Risk / control |
|---|---|---:|---|
| `pwd` / `Get-Location` | Confirm location | No | Must precede write commands |
| `ls` / `Get-ChildItem` | Inspect files | No | Stop if unexpected files appear |
| `git --version` | Confirm Git availability | No | Use official install guidance if missing |
| `git rev-parse --show-toplevel` | Detect current/parent repository before initialization | No | Expected to fail in fresh safe folder; stop if a path is printed |
| `git init` | Initialize local repository | Yes | Practice folder only; does not publish |
| `git status` | Inspect state | No | Run before and after key actions |
| `git add README.md index.html` | Stage explicit files | Yes | No `git add .` in this article |
| `git config user.name/email` | Set practice identity locally | Yes | No `--global`; practice values only |
| `git commit` | Record staged state | Yes | Confirm staged files first |
| `git log --oneline -1` | Inspect latest commit | No | Record short ID only |
| `git diff -- index.html` | Inspect unstaged difference | No | Must precede restore |
| `git restore -- index.html` | Discard uncommitted change in one file | **Yes, destructive** | Disposable practice change only; explicit warning and confirmation |

Forbidden in this article: `git reset --hard`, `git clean`, force push, rebase, bulk staging, any remote command.

## 9. Practical validation record

### Evidence currently available

- 2026-08-17 read-only local check on the current machine: Darwin arm64 and Git 2.42.0 are present.
- 2026-08-17 isolated temporary-directory check on the current Mac: outside a repository, the preflight returned `not a git repository`; inside a harmless test parent repository, it printed that parent path and supported the required stop decision. In the isolated safe directory, `git init`, explicit add, repository-local identity, commit, log, diff, `git restore -- index.html`, and final clean status all completed as drafted.
- This was not a clean-environment or beginner test and does not validate the ChatGPT desktop-app UI.
- No native Windows run was completed.
- The draft must not convert these observations into a cross-platform or beginner-completion claim.

### Required macOS run

- [ ] Clean or documented fresh-user environment and OS version.
- [ ] Current ChatGPT app version/build and integrated-terminal UI.
- [ ] Official Git installation path when Git is absent; no unofficial installer.
- [ ] Every command executed exactly as printed from the correct folder.
- [ ] Parent-repository preflight tested once outside a repository and once inside a harmless test parent repository; path result triggers a stop.
- [ ] Initial `status`, staged `status`, commit output, log, diff, restore, final clean status saved as sanitized evidence.
- [ ] Repository-local identity fallback tested without `--global`.
- [ ] `git restore` data-loss warning and preconditions reviewed by a second person.
- [ ] Browser check of restored HTML completed.
- [ ] Time and observed errors recorded.

### Required native Windows run

- [ ] Clean or documented fresh-user environment and Windows version.
- [ ] Current ChatGPT app version/build and PowerShell integrated terminal.
- [ ] Official Git installation path when Git is absent; app restart behavior recorded.
- [ ] Every command executed exactly as printed from the correct folder.
- [ ] Parent-repository preflight tested once outside a repository and once inside a harmless test parent repository; path result triggers a stop.
- [ ] Initial `status`, staged `status`, commit output, log, diff, restore, final clean status saved as sanitized evidence.
- [ ] Repository-local identity fallback tested without `--global`.
- [ ] `git restore` data-loss warning and preconditions reviewed by a second person.
- [ ] Browser check of restored HTML completed.
- [ ] Path/OneDrive/managed-device differences recorded without exposing personal paths.
- [ ] Time and observed errors recorded.

If either target OS cannot be validated, narrow the article to the verified OS or split the OS-specific steps under a new decision.

## 10. Afterword decision

**Omit.** The completion memo and #4 bridge already provide closure. A reflective afterword would distract from the destructive-operation warning that should remain the final technical takeaway.

## 11. Pre-publication review

### Editorial result

**PASS WITH REQUIRED VALIDATION — the learning sequence and guardrails are coherent.**

### Release result

**NO-GO — `git restore` makes practical cross-OS validation and independent QA mandatory.**

### Review notes

- Accuracy: Core explanations and commands are tied to first-party Git/OpenAI/GitHub documentation.
- Reader fit: The exercise uses the artifact from #2 and avoids GitHub, branching, and production repositories.
- Logic: Inspect location → initialize → create explicit file → stage named files → commit → inspect disposable change → restore.
- Safety: Destructive behavior is named immediately, repeated before execution, and constrained to one disposable file.
- Secret handling: No remote operation, no bulk staging, no real repository, no client/employer data.
- Reproducibility: The expected states are described, but exact outputs, installation behavior, and timing remain unverified.
- Title integrity: “壊さず育てる” is acceptable only because the body rejects automatic protection and universal recovery. Do not strengthen it to “絶対戻せる”.

### Required corrections after validation

1. Replace the `公開前注記` with tested environment/date/version information or remove unsupported OS coverage.
2. Add the exact current UI route to the integrated terminal only after both OS runs; keep a non-UI fallback if practical.
3. Replace target time with measured ranges.
4. Update expected Git wording where macOS and Windows outputs differ.
5. Add only observed error/recovery pairs as verified guidance.
6. Have an independent reviewer verify the parent-repository preflight and that no write command can affect a parent, existing, remote, or unintended repository when followed as written.
7. Recheck official OpenAI material within 48 hours and Git material immediately before publication.

## 12. Human approval checklist

- [ ] 推奨タイトルと「壊さず」の表現を承認した。
- [ ] macOSの通し検証証跡を確認した。
- [ ] Windowsネイティブの通し検証証跡を確認した。
- [ ] 対応OS、Gitバージョン、アプリバージョン、所要時間の表現を承認した。
- [ ] すべてのコマンドが練習フォルダだけを対象とすることを確認した。
- [ ] `git init`前の親リポジトリ検出と、パス表示時の中止・作り直しを確認した。
- [ ] `git add .`、remote操作、`git reset --hard`、`git clean`、force pushが本文にない。
- [ ] `git restore`の警告、対象確認、差分確認、最終確認を承認した。
- [ ] スクリーンショットの権利・匿名化・秘密情報除去を確認した。
- [ ] 独立QAが公開可と判断した。
- [ ] noteの最終プレビューを本人が確認し、手動公開を個別に承認した。
