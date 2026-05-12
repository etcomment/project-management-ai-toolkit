# ChatGPT 向け使い方ガイド

このディレクトリには、ChatGPT で本リポジトリを活用するためのファイルが入っています。

> [!IMPORTANT]
> 顧客情報・個人情報・契約情報・認証情報（APIキー・パスワード等）は、ChatGPT に入力しないでください。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください。

---

## このディレクトリのファイル一覧

| ファイル | 種別 | 内容 |
|---|---|---|
| [project-instructions.md](project-instructions.md) | 設定用・コピー用 | ChatGPT Projects・カスタムGPTの指示欄にコピーして使う指示文 |
| [custom-gpt-instructions.md](custom-gpt-instructions.md) | 設定ガイド＋コピー用 | カスタムGPTの設定手順（人間向けガイド）と、Instructions欄にコピーする文面を含む |
| [use-context-files.md](use-context-files.md) | 人間向けガイド | contexts/ と prompts/ の使い方手順 |
| [examples.md](examples.md) | 人間向けガイド | ChatGPTでの利用例（架空データ） |

---

## どのファイルを事前設定するか

ChatGPTで利用する場合、すべてのファイルを事前設定する必要はありません。

### 事前設定・コピーするファイル

| 用途 | ファイル | 設定先 |
|---|---|---|
| ChatGPT Projects の基本指示 | `project-instructions.md` | Project Instructions |
| カスタムGPTの基本指示 | `custom-gpt-instructions.md` 内の Instructions 欄 | Custom GPT Instructions |
| PM共通前提 | `../contexts/PM_CONTEXT.md` | Knowledge / プロジェクトファイル / チャット冒頭 |
| AI安全ガイド | `../docs/ai-safety.md` | Knowledge / プロジェクトファイル |
| 用途別コンテキスト | `../contexts/*.md` | 必要に応じてKnowledgeまたはチャットに追加 |

### 人間が読むガイド

| 用途 | ファイル |
|---|---|
| ChatGPTでの全体的な使い方 | `README.md` |
| コンテキストファイルの使い方 | `use-context-files.md` |
| 利用例 | `examples.md` |
| カスタムGPTの作成手順 | `custom-gpt-instructions.md` の設定ガイド部分 |

---

## 利用パターン別の案内

### ChatGPT Projects で使う場合

1. ChatGPT でプロジェクトを新規作成する
2. プロジェクトの「Instructions」に `project-instructions.md` の内容を貼り付ける
3. 案件情報（マスキング済み）を入力して依頼する
4. 用途別コンテキストは `use-context-files.md` を参照して追加する

### カスタムGPT で使う場合

`custom-gpt-instructions.md` を参照してください。カスタムGPTの設定方法、Instructions欄の文面、Conversation startersの例、Knowledgeに追加するファイルの推奨一覧を記載しています。

### 通常チャットで使う場合

1. `contexts/PM_CONTEXT.md` の内容をコピーする
2. 新規チャットの最初のメッセージに貼り付ける
3. 用途別コンテキストと案件情報（マスキング済み）を続けて入力する
4. 詳細手順は `use-context-files.md` を参照する

---

## contexts/ と prompts/ の使い分け

| ディレクトリ | 役割 |
|---|---|
| `contexts/` | AIに読み込ませる前提情報・判断軸・業務ルール |
| `prompts/` | 用途別の依頼文テンプレート（入力欄付き） |

基本的な流れ：

1. `contexts/PM_CONTEXT.md`（共通前提）を読み込ませる
2. 目的に合った `contexts/` のファイルを追加する
3. `prompts/` のテンプレートを使って依頼文を組み立てる
4. 案件情報をマスキングしてから入力する

---

## 関連ドキュメント

- [docs/for-chatgpt.md](../docs/for-chatgpt.md) — ChatGPT向け使い方（詳細）
- [docs/ai-safety.md](../docs/ai-safety.md) — AIに入力してよい情報・安全な使い方
- [DISCLAIMER.md](../DISCLAIMER.md) — 免責事項
