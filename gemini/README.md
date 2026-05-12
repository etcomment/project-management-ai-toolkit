# Gemini 向け使い方ガイド

このディレクトリには、Gemini で本リポジトリを活用するためのファイルが入っています。

> [!IMPORTANT]
> 顧客情報・個人情報・契約情報・認証情報（APIキー・パスワード等）は、Gemini に入力しないでください。
> AI出力は業務判断の代替ではありません。出力内容は必ず人間が確認・修正してください。

---

## このディレクトリのファイル一覧

| ファイル | 種別 | 内容 |
|---|---|---|
| [gemini-instructions.md](gemini-instructions.md) | 設定用・コピー用 | Gemini / Gems の指示欄にコピーして使う指示文 |
| [gem-setup-guide.md](gem-setup-guide.md) | 設定ガイド＋コピー用 | Gemの設定手順（人間向けガイド）と、指示欄にコピーする文面を含む |
| [use-context-files.md](use-context-files.md) | 人間向けガイド | contexts/ のコンテキストファイルの使い方手順 |
| [examples.md](examples.md) | 人間向けガイド | Geminiでの利用例（架空データ） |

---

## どのファイルを事前設定するか

Geminiで利用する場合、すべてのファイルを事前設定する必要はありません。

### 事前設定・コピーするファイル

| 用途 | ファイル | 設定先 |
|---|---|---|
| Gemini / Gems の基本指示 | `gemini-instructions.md` | Gemの指示欄 / チャット冒頭 |
| Gemの設定文 | `gem-setup-guide.md` 内の「Gems の指示欄に貼る文面」 | Gemの指示欄 |
| PM共通前提 | `../contexts/PM_CONTEXT.md` | チャット冒頭 / Gem利用時の参照情報 |
| AI安全ガイド | `../docs/ai-safety.md` | チャット冒頭 / 参照情報 |
| 用途別コンテキスト | `../contexts/*.md` | 必要に応じてチャットに追加 |

### 人間が読むガイド

| 用途 | ファイル |
|---|---|
| Geminiでの全体的な使い方 | `README.md` |
| Gemの作成手順 | `gem-setup-guide.md` の設定ガイド部分 |
| コンテキストファイルの使い方 | `use-context-files.md` |
| 利用例 | `examples.md` |

---

## 利用フロー

```text
Geminiで使う
│
├─ 通常チャットで使う
│    └─ contexts/*.md をチャットに貼り付ける
│
└─ Gemsで使う
     └─ gemini-instructions.md / gem-setup-guide.md を参考に設定する

共通の流れ：
PM_CONTEXT.md
   ↓
用途別 contexts/*.md
   ↓
案件情報をマスキングして入力
   ↓
AI出力を人間が確認
```

> [!NOTE]
> Google Workspaceで利用する場合は、組織のポリシーおよびデータ利用条件を事前に確認してください。

---

## 利用パターン別の案内

### Gemini の通常チャットで使う場合

1. `contexts/PM_CONTEXT.md` の内容をコピーする
2. Gemini で新しいチャットを開く
3. チャットの冒頭にコンテキストの内容を貼り付ける
4. 用途別コンテキストと案件情報（マスキング済み）を続けて入力する
5. 詳細手順は `use-context-files.md` を参照する

### Gems で使う場合

`gem-setup-guide.md` を参照してください。Gems の設定方法、指示欄の文面、参照ファイルの推奨一覧を記載しています。

---

## contexts/ の使い方

`contexts/` の各ファイルには、AIへの前提情報・判断軸・業務ルールに加えて、Prompt Template が内包されています。

基本的な流れ：

1. `contexts/PM_CONTEXT.md`（共通前提）を読み込ませる
2. 目的に合った `contexts/` のファイルを追加する
3. 各コンテキストファイル末尾の Prompt Template を参考に依頼文を組み立てる
4. 案件情報をマスキングしてから入力する

---

## 関連ドキュメント

- [docs/for-gemini.md](../docs/for-gemini.md) — Gemini向け使い方（詳細）
- [docs/ai-safety.md](../docs/ai-safety.md) — AIに入力してよい情報・安全な使い方
- [DISCLAIMER.md](../DISCLAIMER.md) — 免責事項
